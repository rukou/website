---
layout: docs
title: Dependency Generator
category: Local Layer
order: 400
---
<script async src="/assets/jszip.min.js"></script>
<script async src="/assets/rawinflate.js"></script>
<p class="text-warning bg-dark pt-2 pb-2 pl-4">Note : your browser will process the zip file. It can take some time depending on the file size.</p>

<input type="file" id="file" name="file" multiple /><br />

<div id="timing"></div>
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" data-toggle="tab" href="#result_configmap">kubernetes config map</a>
  </li>
  <li class="nav-item">
    <a class="nav-link"  data-toggle="tab" href="#result_envvars">kubernetes env variable</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-toggle="tab" href="#result_bash">bash script</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-toggle="tab" href="#result_table">result table</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-toggle="tab" href="#result_ij">IntelliJ</a>
  </li>
</ul>
<div class="tab-content" >
  <pre id="result_configmap" class="tab-pane fade show active"></pre>
  <pre id="result_envvars" class="tab-pane fade" ></pre>
  <pre id="result_bash" class="tab-pane fade" ></pre>
  <table border="1" id="result_table" style="overflow-wrap: anywhere;" class="tab-pane fade" ></table>
  <pre id="result_ij" class="tab-pane fade" ></pre>
</div>
<script>
var result_configmap = $("#result_configmap");
var result_envvars = $("#result_envvars");
var result_bash = $("#result_bash");
var result_ij = $("#result_ij");
var result_table = $("#result_table");
var timing = $("#timing");
var fileList = [];
$("#file").on("change", function(evt) {
  // remove content
  result_configmap.html("");
  result_envvars.html("");
  result_bash.html("");
  result_table.html("");
  result_ij.html("");
    // Closure to capture the file information.
    function handleFile(f) {
        var dateBefore = new Date();
        JSZip.loadAsync(f)                                   // 1) read the Blob
        .then(function(zip) {
            zip.forEach(function (relativePath, zipEntry) {  // 2) print entries
              //check for directory
              if(!zipEntry.dir){
                let compressed = String.fromCharCode.apply(null, zipEntry._data.compressedContent);
                let uncompressed = RawDeflate.inflate(compressed)
                fileList.push({
                  name: zipEntry.name,
                  b64: btoa(uncompressed),
                  envname: `CLASS_${zipEntry.name.replace('.class','').toUpperCase().replace(/\//g,'_').replace(/\./g,'_')}`});
              }
            });
            //render output
            let table_str='<tr><th style="width:50%;">environment variable</th><th>value</th></tr>';
            let ij_str='';
            let bash_str='';
            let env_str='';
            let map_str=`apiVersion: v1
kind: ConfigMap
metadata:
  name: rukou-config
  namespace: default
data:
`;
            for(let idx=0;idx<fileList.length;idx++){
              let item = fileList[idx];
              table_str+=`<tr><td>${item.envname}</td><td>${item.b64}</td></tr>`;
              bash_str+=`export ${item.envname}=${item.b64}\n`;
              ij_str+=`${item.envname}=${item.b64}\n`;
              env_str+=`- name: ${item.envname}
  value: '${item.b64}'
`;
              map_str+=`  ${item.envname}: '${item.b64}'
`;
            }
            result_table.html(table_str);
            result_bash.html(bash_str);
            result_configmap.html(map_str+`\n\n`);
            result_ij.html(ij_str+`\n\n`);
            result_envvars.html(env_str);
            var dateAfter = new Date();
            timing.html(`loaded in ${dateAfter - dateBefore} ms`);
        }, function (e) {
            timing.append($("<div>", {
                "class" : "alert alert-danger",
                text : "Error reading " + f.name + ": " + e.message
            }));
        });
    }
    var files = evt.target.files;
    for (var i = 0; i < files.length; i++) {
        handleFile(files[i]);
    }
});
</script>
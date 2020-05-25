---
layout: docs
title: Configuration
category: Local Layer
order: 200
---
The local layer is build for any container runtime. Therefore all configuration is handled through environment variables.

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| SOURCE_TYPE | router layer type | google-pubsub |
| SOURCE_EDGE2LOCALSUBSCRIPTION | name of the topic subscription | |
| SOURCE_SERVICEACCOUNT | account as inline json string | |

### External Dependencies

If the Local Layer needs external dependencies like for example proprietary JAR-files for JMS, there are two ways to add those to the Layer.

#### Option 1 - Provide Classes as Environment Variable

The Local Layer has a special ClassLoader, which will look for classes defined through environment variables.

for example: 
    /io/rukou/Whatever.class
can be provided through the following variable
    CLASS_IO_RUKOU_WHATEVER

The content of this variable needs to be a base64 representation of the file content.

To generate this kind of variables, we build a website which can do this task locally.

#### Option 2 - Overlay the container image

To add JAR-files to the image, those only file must be placed in the `/opt/rukou` directory.

All JAR-files in that directory are placed on the classpath.

<style>
td, th {
    border: 1px solid var(--secondary)
}
</style>
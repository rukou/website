---
layout: docs
title: Limitations
category: General
order: 500
---
Rùkǒu has the following limitations.

Only Request/Reply is supported.

| feature | value |
| ------- | ----- |
| Request Timeout | 30 seconds |

## Routing Layer Limits

### Message Size

| feature | Google PubSub | Azure ServiceBus | 
| :-: | :-:| :-: |
| message size | 10MB | 1MB |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>
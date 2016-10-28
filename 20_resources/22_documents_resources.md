## 2.2. [Documents Resources](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#doctransfer) {#2-2-documents-resources}

**Requirements**

| ID | Requirement |
| --- | --- |
| XAPI-00182 | An LRS makes no modifications to stored data for any rejected request. |
| XAPI-00183 | A Document Merge only performs overwrites at one level deep, although the entire object is replaced. |
| XAPI-00184 | A Document Merge overwrites any duplicate values from the previous document with the new document. |
| XAPI-00185 | A Document Merge re-serializes all Objects to finalize a single document |
| XAPI-00186 | A Document Merge de-serializes all Objects represented by each document before making other changes. |
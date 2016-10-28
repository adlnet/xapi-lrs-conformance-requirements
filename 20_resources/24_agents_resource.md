## 2.4. [Agents Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#agentsres) {#2-4-agents-resource}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00236 | An LRS&#039;s Agents API accepts GET requests with response 200 OK, Person Object |
| XAPI-00237 | A Person Object&#039;s &quot;objectType&quot; property is a String and is &quot;Person&quot; The LRS must return a valid “objectType” string. |
| XAPI-00238 | A Person Object&#039;s &quot;name&quot; property is an Array of Strings. The LRS must return a “name” property with a valid Array of Strings, if present. |
| XAPI-00239 | A Person Object&#039;s &quot;mbox&quot; property is an Array of IRIs. The LRS must return an “mbox” property with a valid array of IRIs, if present. |
| XAPI-00240 | A Person Object&#039;s &quot;mbox_sha1sum&quot; property is an Array of Strings. The LRS must return a Person Object which has a “mbox_sha1sum” and is valid array of strings, if present. |
| XAPI-00241 | A Person Object&#039;s &quot;openid&quot; property is an Array of Strings The LRS must return a “openid” value which is valid array of strings, if present. |
| XAPI-00242 | A Person Object&#039;s &quot;account&quot; property is an Array of Account Objects The LRS must return a Person Object with a “name” value which is a valid array of account objects, if present. |
| XAPI-00243 | An LRS&#039;s Agents API rejects a GET request without &quot;agent&quot; as a parameter with error code 400 Bad Request |
| XAPI-00244 | A Person Object&#039;s &quot;mbox&quot; entries have the form &quot;mailto:emailaddress&quot;. The LRS must return a Person Object which has a “mbox” value with the form &quot;mailto:emailaddress&quot; |
| XAPI-00245 | An LRS has an Agents API with endpoint &quot;base IRI&quot; + /agents&quot; |
| XAPI-00246 | The Agents Resource MUST have an endpoint which accepts GET requests and returns a special, Person Object where each attribute has an array value and it is legal to include multiple identifying properties. |
| XAPI-00247 | If an LRS does not have any additional information about an Agent to return from the Agents Resource, the LRS MUST still return a Person when queried, but that Person Object will only include the information associated with the requested Agent. |
| XAPI-00248 | An LRS&#039;s Agents API upon processing a successful GET request returns a Person Object based on matched data from the &quot;agent&quot; parameter and code 200 OK |
| XAPI-00249 | An LRS&#039;s Agents API rejects a GET request with &quot;agent&quot; as a parameter if it is not a valid (in structure) Agent with error code 400 Bad Request |
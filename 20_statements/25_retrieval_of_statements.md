## 2.5. [Retrieval of Statements](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#retrieval) {#2-5-retrieval-of-statements}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00108 | If not empty, the &quot;more&quot; property&#039;s IRL refers to a specific container object corresponding to the next page of results from the original GET request. To test make a GET request which will return a known number of statements and confirm the LRS returns a “more” property which has an IRL with a container of the remaining statements and that the IRL is valid. |
| XAPI-00109 | The &quot;more&quot; property is absent or an empty string (no whitespace) if the entire results of the original GET request have been returned. To test make a GET request which will return a known number of statements and check to make sure the LRS either returns an empty string or the more property is absent. |
| XAPI-00110 | A &quot;statements&quot; property is an Array of Statements. Make a GET request which will return at least one statement and confirm the “statements” property is a valid Array of Statements. |
| XAPI-00111 | A &quot;more&quot; property&#039;s referenced container object follows the same rules as the original GET request, originating with a single &quot;statements&quot; property and a single &quot;more&quot; property. |
| XAPI-00112 | The LRS will NOT reject a GET request which returns an empty &quot;statements&quot; property. Send a GET request which will not return any results and check that a 200 Ok and an empty StatementResult Object is returned. |
| XAPI-00113 | An LRS&#039;s Statement API, upon processing a successful GET request, will return a single &quot;statements&quot; property and a single &quot;more&quot; property. A single &quot;more&quot; property must be present if there are additional results available. |
| XAPI-00114 | A &quot;statements&quot; property result which is paginated will create a container for each additional page. |
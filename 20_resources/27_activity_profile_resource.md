## 2.7. [Activity Profile Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#actprofres) {#2-7-activity-profile-resource}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00285 | An LRS&#039;s Activity Profile API upon processing a successful DELETE request deletes the associated profile and returns code 204 No Content |
| XAPI-00286 | An LRS&#039;s Activity Profile API upon processing a successful POST request returns code 204 No Content |
| XAPI-00287 | An LRS&#039;s Activity Profile API upon processing a successful PUT request returns code 204 No Content |
| XAPI-00288 | An LRS&#039;s Activity Profile API upon processing a successful GET request with a valid &quot;profileId&quot; as a parameter returns the document satisfying the requirements of the GET and code 200 OK |
| XAPI-00289 | An LRS&#039;s Activity Profile API upon processing a successful GET request without &quot;profileId&quot; as a parameter returns an array of ids of activity profile documents satisfying the requirements of the GET and code 200 OK |
| XAPI-00290 | An LRS&#039;s Activity Profile API accepts GET requests |
| XAPI-00291 | An LRS&#039;s Activity Profile API accepts DELETE requests |
| XAPI-00292 | An LRS&#039;s Activity Profile API accepts POST requests |
| XAPI-00293 | An LRS&#039;s Activity Profile API accepts PUT requests |
| XAPI-00294 | The Activity Profile API&#039;s returned array of ids from a successful GET request all refer to documents stored after the TimeStamp in the &quot;since&quot; parameter of the GET request if such a parameter was present |
| XAPI-00295 | An LRS&#039;s Activity Profile API rejects a GET request with &quot;since&quot; as a parameter if it is not a &quot;TimeStamp&quot;, with error code 400 Bad Request |
| XAPI-00296 | An LRS&#039;s Activity Profile API rejects a GET request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00297 | An LRS&#039;s Activity Profile API rejects a DELETE request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00298 | An LRS&#039;s Activity Profile API rejects a POST request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00299 | An LRS&#039;s Activity Profile API rejects a PUT request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00300 | An LRS&#039;s Activity Profile API rejects a DELETE request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00301 | An LRS&#039;s Activity Profile API rejects a POST request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00302 | An LRS&#039;s Activity Profile API rejects a PUT request without &quot;profileId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00303 | An LRS&#039;s Activity Profile API can process a GET request with &quot;since&quot; as a parameter. Returning 200 OK and all matching profiles after the date/time of the “since” parameter. |
| XAPI-00304 | An LRS&#039;s Activity Profile API rejects a GET request with &quot;agent&quot; as a parameter if it is not in JSON format with error code 400 Bad Request (format, 7.4.table2.row2.a) |
| XAPI-00305 | An LRS&#039;s Activity Profile API rejects a DELETE request with &quot;profileId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request (format, 7.5.table2.row2.a) |
| XAPI-00306 | An LRS&#039;s Activity Profile API API rejects a POST request with &quot;profileId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request (format, 7.5.table2.row2.a) |
| XAPI-00307 | An LRS&#039;s Activity Profile API rejects a PUT request with &quot;profileId&quot; as a parameter if it is not type &quot;String&quot; with error code 400 Bad Request (format, 7.5.table2.row2.a) |
| XAPI-00308 | An LRS&#039;s Activity Profile API performs a Document Merge if a activityId is found and both it and the document in the POST request have type &quot;application/json&quot; If the merge is successful, the LRS MUST respond with HTTP status code 204 No Content. |
| XAPI-00309 | An LRS&#039;s Activity Profile API, rejects a POST request if the document is found and either document&#039;s type is not &quot;application/json&quot; with error code 400 Bad Request |
| XAPI-00310 | An LRS&#039;s Activity Profile API, upon receiving a POST request for a document not currently in the LRS, treats it as a PUT request and store a new document. Returning 204 No Content |
| XAPI-00311 | An LRS has an Activity Profile API with endpoint &quot;base IRI&quot;+&quot;/activities/profile&quot; |
| XAPI-00312 | An LRS will accept a POST request to the Activity Profile API |
| XAPI-00313 | An LRS&#039;s Activity Profile API, rejects a POST request if the document is found and either document is not a valid JSON Object |
| XAPI-00314 | An LRS must reject, with 400 Bad Request, a POST request to the Activity Profile API which contains name/value pairs with invalid JSON and the Content-Type header is &quot;application/json |
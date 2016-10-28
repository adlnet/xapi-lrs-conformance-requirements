## 2.5. [Activities Resource](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Communication.md#activitiesres) {#2-5-activities-resource}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00250 | An LRS&#039;s Activities API rejects a GET request without &quot;activityId&quot; as a parameter with error code 400 Bad Request |
| XAPI-00251 | An LRS&#039;s Activities API upon processing a successful GET request returns 200 OK and the complete Activity Object |
| XAPI-00252 | An LRS has an Activities API with endpoint &quot;base IRI&quot; + /activities&quot; (7.5) Implicit (in that it is not named this by the spec) |
| XAPI-00253 | An LRS&#039;s Activities API accepts GET requests |
| XAPI-00254 | The Activity Object must contain all available information about an activity from any statements who target the same “activityId”. For example, LRS accepts two statements each with a different language description of an activity using the exact same “activityId”. The LRS must return both language descriptions when a GET request is made to the Activities endpoint for that “activityId”. |
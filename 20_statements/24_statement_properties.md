## 2.4. [Statement Properties](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#statement-properties) {#2-4-statement-properties}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00021 | All Statement properties must be used at most one time. An LRS rejects with 400 Bad Request a statement that contains a JSON object with a duplicate key. |
| XAPI-00022 | A &quot;timestamp&quot; property is a TimeStamp, per section 4.5\. An LRS rejects with 400 Bad Request a statement if it has a TimeStamp and that TimeStamp is invalid. |
| XAPI-00023 | A &quot;stored&quot; property is a TimeStamp, per section 4.5\. An LRS assigns the “stored” property upon receipt with a valid TimeStamp. |
| XAPI-00024 | An &quot;authority&quot; property is an Agent or Group. An LRS rejects with 400 Bad Request a statement which has an “authority” property which is not Agent or Group. |
| XAPI-00025 | A Statement&#039;s &quot;attachments&quot; property is an array of Attachments. An LRS rejects with 400 Bad Request a statement which has an “attachments” property which is not an array of attachments. |

### 

### 2.4.1. [ID](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#stmtid) {#2-4-1-id}

**Requirements**

| ID | Requirement |
| --- | --- |
| XAPI-00026 | An LRS generates the &quot;id&quot; property of a Statement if none is provided (Modify, 4.1.1.a) |
| XAPI-00027 | A Statement&#039;s &quot;id&quot; property is a UUID following RFC 4122\. An LRS rejects with 400 Bad Request a statement which has an “id” and that “id” is invalid. |
| XAPI-00028 | A Statement&#039;s &quot;id&quot; property is a String. An LRS rejects with 400 Bad Request a statement which has an “id” and that property is not a string |
| XAPI-00029 | All UUID types are in standard String form. An LRS rejects with 400 Bad Request a statement which has an property which is required to be a UUID and that property is not in standard string form |
| XAPI-00030 | All UUID types follow requirements of RFC4122\. An LRS rejects with 400 Bad Request a statement which has a property which is required to be a UUID and does not follow RFC4122\. |

###  {#-0}

###  {#-1}

### 2.4.2. [Actor](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#actor) {#2-4-2-actor}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00031 | An &quot;actor&quot; property&#039;s &quot;objectType&quot; property is either &quot;Agent&quot; or &quot;Group&quot; An LRS rejects with 400 Bad Request an actor with an “objectType” which is not “Agent” or “Group” |

#### 2.4.2.1 [When the Actor objectType is Agent](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2421-when-the-actor-objecttype-is-agent) {#2-4-2-1-when-the-actor-objecttype-is-agent}

**Definition**

1.  An Agent is defined as an Actor with &quot;objectType&quot; of an &quot;Agent&quot;, an instructor with &quot;objectType&quot; of an &quot;Agent&quot;, or &quot;object&quot; property with value &quot;Agent&quot;

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00032 | An &quot;objectType&quot; property is a String. If present, the LRS must validate and reject with 400 Bad Request if invalid |
| XAPI-00033 | A &quot;name&quot; property is a String. If present, the LRS must validate and reject with 400 Bad Request if invalid. |
| XAPI-00034 | An &quot;actor&quot; property with &quot;objectType&quot; as &quot;Agent&quot; uses exactly one of the following Inverse Functional Identifier properties: &quot;mbox&quot;, &quot;mbox_sha1sum&quot;, &quot;openid&quot;, &quot;account&quot;. An LRS rejects with 400 Bad Request any agent object: |

####  {#-14}

####  {#-15}

####  {#-16}

#### 2.4.2.2 [When the Actor ObjectType is Group](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2422-when-the-actor-objecttype-is-group) {#2-4-2-2-when-the-actor-objecttype-is-group}

**Definition**

1.  An anonymous Group is defined when at least one of the following is true:
    *   An “actor” property with “objectType” of “group” with the “member” property present, but without an IFI
    *   A “context” object with a “team” property of “group” with the “member” property present
    *   An “object” with the value “Group” with the “member” property present.
2.  An identified Group is defined when at least one of the following is true:
    *   An “actor” property with “objectType” of “group” and an IFI present
    *   A “context” object with a “team” property of “group” and an IFI is present
    *   An “object” with the value “Group” and an IFI present

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00035 | A Group uses the &quot;member&quot; property. An LRS rejects with 400 Bad Request if the “member” property is present anywhere but in a group object (Actor or team). |
| XAPI-00036 | The &quot;member&quot; property is an array of Objects following Agent requirements. An LRS rejects with 400 Bad Request any group object which has a member property with anything other than a valid array of Agents as a value |
| XAPI-00037 | An &quot;actor&quot; property with &quot;objectType&quot; as &quot;Group&quot; uses exactly one of the following Inverse Functional Identifier properties: &quot;mbox&quot;, &quot;mbox_sha1sum&quot;, &quot;openid&quot;, &quot;account&quot; or a member property with at least one Agent. An LRS rejects with 400 Bad Request any group object with: |

####  {#-17}

#### 2.4.2.3 [Inverse Functional Identifier](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2423-inverse-functional-identifier) {#2-4-2-3-inverse-functional-identifier}

**Definition**

An Inverse Functional Identifier (IFI) is a value of an Agent or Identified Group that is guaranteed to only ever refer to that Agent or Identified Group.

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00038 | An &quot;mbox&quot; property has the form &quot;mailto:email address&quot; and is an IRI. An LRS rejects with 400 Bad Request if a statement that uses the “mbox” IFI is an invalid form. |
| XAPI-00039 | An &quot;mbox_sha1sum&quot; property is a String An LRS rejects with 400 Bad Request if a statement uses the “mbox_sha1sum” IFI and it is not a valid string. |
| XAPI-00040 | An &quot;openid&quot; property is a URI. An LRS rejects with 400 Bad Request if a statement uses the “openID” IFI and the URI is invalid. |
| XAPI-00041 | An “account” property is an object. An LRS rejects with 400 Bad Request if a statement uses an invalid Account Object. A valid account is defined by the requirements listed in XAPI-I-63 and XAPI-I-66 |

####  {#-18}

#### 2.4.2.4 [Account Object](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2424-account-object) {#2-4-2-4-account-object}

**Definition**

1.  An Account Object is the &quot;account&quot; property of a Group or Agent

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00042 | An Account Object&#039;s homePage&quot; property is an IRL. An LRS rejects with 400 Bad Request if a statement uses the “account” IFI and the “homePage” property is absent or has an invalid IRL. |
| XAPI-00043 | An Account Object &quot;name&quot; property is a String. An LRS rejects with 400 Bad Request if a statement uses the “account” IFI and the “name” property is absent or has an invalid string. |

###  {#-2}

### 2.4.3. [Verb](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#verb) {#2-4-3-verb}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00044 | A &quot;verb&quot; object contains an &quot;id&quot; property which is required to be an IRI. An LRS rejects with 400 Bad Request if a statement uses the Verb Object and “id” is absent or “id” is present, but the value is an invalid IRI. |
| XAPI-00045 | A &quot;verb&quot; property&#039;s &quot;display&quot; property is a Language Map. An LRS rejects with 400 Bad Request if a statement uses the Verb Object’s “display” property and it is not a valid Language Map. |

###  {#-3}

###  {#-4}

###  {#-5}

### 2.4.4. [Object](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#object) {#2-4-4-object}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00046 | An &quot;object&quot; property&#039;s &quot;objectType&quot; property is either &quot;Activity&quot;, &quot;Agent&quot;, &quot;Group&quot;, &quot;SubStatement&quot;, or &quot;StatementRef&quot;. An LRS rejects with 400 Bad Request an “object” property with an objectType which is not &quot;Activity&quot;, &quot;Agent&quot;, &quot;Group&quot;, &quot;SubStatement&quot;, or &quot;StatementRef&quot;. |

####  {#-19}

#### 2.4.4.1 [When the ObjectType is Activity](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2441-when-the-objecttype-is-activity) {#2-4-4-1-when-the-objecttype-is-activity}

**Definition**

1.  An Activity is defined by an &quot;object&quot; without &quot;objectType&quot; or with &quot;objectType&quot; having the value &quot;Activity&quot;
2.  An Activity Definition is defined as the contents of a &quot;definition&quot; property object of an Activity

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00047 | An &quot;object&quot; property uses the &quot;id&quot; property exactly one time. The LRS must reject with 404 Bad Request an otherwise legal statement if the object&#039;s objectType is Activity and the object&#039;s “id” is not an IRI or the object’s “id” is absent |
| XAPI-00048 | An &quot;object&quot; property uses the &quot;definition&quot; property at most one time. The LRS rejects with 400 Bad Request an otherwise legal statement if the object&#039;s “definition” property is an invalid object. |
| XAPI-00049 | An Activity Definition&#039;s &quot;interactionType&quot; property is a String with a value of either true-false, choice, fill-in, long-fill-in, matching, performance, sequencing, likert, numeric or other. An LRS rejects with 400 Bad Request an Activity Definition&#039;s &quot;interactionType&quot; property if it is not a string value of true-false, choice, fill-in, long-fill-in, matching, performance, sequencing, likert, numeric or other. |
| XAPI-00050 | An Activity Definition&#039;s &quot;correctResponsesPattern&quot; property is an array of Strings. An LRS rejects with 400 Bad Request an Activity Definition&#039;s &quot;correctResponsesPattern&quot; property if present, and if it is not a valid array of strings. |
| XAPI-00051 | An Activity Definition&#039;s &quot;steps&quot; property is an array of Interaction Components. An LRS rejects with 400 Bad Request if an Activity Definition&#039;s &quot;steps&quot; property if present, and is not a valid array of Interaction Components. |
| XAPI-00052 | An Activity Definition&#039;s &quot;target&quot; property is an array of Interaction Components. An LRS rejects with 400 Bad Request if an Activity Definition&#039;s &quot;target&quot; property if present, and is not a valid array of Interaction Components. |
| XAPI-00053 | An Activity Definition&#039;s &quot;source&quot; property is an array of Interaction Components. An LRS rejects with 400 Bad Request if an Activity Definition&#039;s &quot;source&quot; property if present, and is not a valid array of Interaction Components. |
| XAPI-00054 | An Activity Definition&#039;s &quot;scale&quot; property is an array of Interaction Components, An LRS rejects with 400 Bad Request if an Activity Definition&#039;s &quot;scale&quot; property if present, and is not a valid array of Interaction Components. |
| XAPI-00055 | An Activity Definition&#039;s &quot;choices&quot; property is an array of Interaction Components. An LRS rejects with 400 Bad Request if an Activity Definition&#039;s &quot;choices&quot; property if present, and is not a valid array of Interaction Components. |
| XAPI-00056 | An Activity Definition&#039;s &quot;name&quot; property is a Language Map. The LRS rejects with 400 Bad Request an otherwise legal statement if the Activity Definition&#039;s &quot;name&quot; property is present and is an invalid Language Map. |
| XAPI-00057 | An Activity Definition&#039;s &quot;extension&quot; property is an Object. The LRS rejects with 400 Bad Request an otherwise legal statement if the Activity Definition&#039;s &quot;extension&quot; property is present and is an invalid Extension Object. |
| XAPI-00058 | Within an array of Interaction Components, the &quot;id&quot; property is a string which is required and unique (within the specific interaction array). The LRS rejects with 400 Bad Request an interaction activity with an array of interaction components in which the “id” property is absent, duplicative, or an invalid string. |
| XAPI-00059 | An Activity Definition&#039;s &quot;description&quot; property is a Language Map. The LRS rejects with 400 Bad Request an otherwise legal statement if the Activity Definition&#039;s &quot;description&quot; property is present and is an invalid Language Map. |
| XAPI-00060 | An Activity Definition&#039;s &quot;type&quot; property is an IRI. The LRS rejects with 400 Bad Request an otherwise legal statement if the Activity Definition&#039;s &quot;type&quot; property is present and is an invalid IRI. |
| XAPI-00061 | An Activity Definition&#039;s &quot;moreinfo&quot; property is an IRL. The LRS rejects with 400 Bad Request an otherwise legal statement if the Activity Definition&#039;s &quot;moreinfo&quot; property is present and is an invalid IRL. |
| XAPI-00062 | An Interaction Component’s &quot;description&quot; property is a Language Map. The LRS rejects with 400 Bad Request an otherwise legal statement if the Interaction Component&#039;s &quot;description&quot; property is present and is an invalid Language Map. |
| XAPI-00063 | An individual Interaction Component, within the array of Interaction Components, is an Object. The LRS rejects with 400 Bad Request an otherwise legal statement if the Interaction Component is present and is an invalid Object. |
| XAPI-00064 | An Activity Definition uses the &quot;interactionType&quot; property if correctResponsesPattern is present. An LRS rejects a statement with 400 Bad Request if a correctResponsePattern is present and interactionType is not. |

####  {#-20}

####  {#-21}

####  {#-22}

#### 2.4.4.2 [When the &quot;Object&quot; is an Agent or a Group](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2442-when-the-object-is-an-agent-or-a-group) {#2-4-4-2-when-the-object-is-an-agent-or-a-group}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00065 | Statements that use an Agent or Group as an Object MUST specify an &quot;objectType&quot; property. The LRS rejects with 400 Bad Request if the “objectType” property is absent and the Object is an Agent Object or Group Object. |

####  {#-23}

####  {#-24}

####  {#-25}

#### 2.4.4.3 [When the &quot;Object&quot; is a Statement](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2443-when-the-object-is-a-statement) {#2-4-4-3-when-the-object-is-a-statement}

**Definition**

1.  A Statement Reference is defined by the &quot;objectType&quot; of an &quot;object&quot; with value &quot;StatementRef&quot;
2.  A Sub-Statement is defined by the &quot;objectType&quot; of an &quot;object&quot; with value &quot;SubStatement&quot;

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00066 | A Sub-Statement follows the requirements of all Statements. The LRS rejects with 400 Bad Request a Statement with a Sub-Statement with any invalid statement properties in an otherwise valid sub-statement. |
| XAPI-00067 | A Sub-Statement cannot use the &quot;authority&quot; property. The LRS rejects with 400 Bad Request a Statement with a Sub-Statement where the “authority” property is present. |
| XAPI-00068 | A Sub-Statement cannot use the &quot;version&quot; property. The LRS rejects with 400 Bad Request a Statement with a Sub-Statement where the “version” property is present. |
| XAPI-00069 | A Sub-Statement cannot use the &quot;stored&quot; property. The LRS rejects with 400 Bad Request a Statement with a Sub-Statement where the “stored” property is present. |
| XAPI-00070 | A Sub-Statement cannot use the &quot;id&quot; property at the Statement level The LRS rejects with 400 Bad Request a Statement with a Sub-Statement where the “id” property is present. |
| XAPI-00071 | A Sub-Statement cannot have a Sub-Statement. The LRS rejects with 400 Bad Request a Statement with a Sub-Statement which contains a Sub-Statement. |
| XAPI-00072 | A Statement Reference&#039;s &quot;id&quot; property is a UUID. The LRS rejects with 400 Bad Request a Statement Reference Object with an “id” property which is absent or an invalid UUID. |
| XAPI-00073 | Statements that have a StatementRef or Sub-Statement as an Object MUST specify an &quot;objectType&quot; property. The LRS rejects with 400 Bad Request if the “objectType” property is absent and the Object is a StatementRef or Sub-Statement. |

###  {#-6}

### 2.4.5. [Result](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#result) {#2-4-5-result}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00074 | A &quot;success&quot; property is a Boolean. The LRS rejects with 400 Bad Request a Statement which has a Result Object with a “success” property which does not have a valid Boolean value, if present. |
| XAPI-00075 | A &quot;completion&quot; property is a Boolean. The LRS rejects with 400 Bad Request a Statement which has a Result Object with a “completion” property which does not have a valid Boolean value, if present. |
| XAPI-00076 | A &quot;response&quot; property is a String. The LRS rejects with 400 Bad Request a Statement which has a Result Object with a “response” property which does not have a valid String value, if present. |
| XAPI-00077 | A &quot;duration&quot; property is a formatted to ISO 8601 durations (see part 3, section 4.6). The LRS rejects with 400 Bad Request a Statement which has a Result Object with a “duration” property which does not have a valid ISO 8601 value, if present. |
| XAPI-00078 | An &quot;extensions&quot; property is an Object. The LRS rejects with 400 Bad Request a Statement which has a Result Object with aa “extensions” property which does not have a valid Extensions Object, if present. |

####  {#-26}

#### 2.4.5.1 [Score](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2451-score) {#2-4-5-1-score}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00079 | A &quot;score&quot; property is an Object. The LRS rejects with 400 Bad Request a “score” property which is not a valid object. |
| XAPI-00080 | If the &quot;score&quot; Object uses the &quot;max&quot; property, the value must be a decimal number more than the &quot;min&quot; property, if it is present. If &quot;min&quot; is not present &quot;max&quot; can be any number. The LRS rejects with 400 Bad Request a statement with a Result Object using the “max” property (if it is present) which is not a decimal number or is lesser than the value of the “min” property, if it is present. |
| XAPI-00081 | If the &quot;score&quot; Object uses the &quot;min&quot; property, the value must be a decimal number less than the &quot;max&quot; property, if it is present. If &quot;max&quot; is not present &quot;min&quot; can be any number. The LRS rejects with 400 Bad Request a statement with a Result Object using the “min” property (if it is present) which is not a decimal number or is greater than the value of the “max” property, if it is present. |
| XAPI-00082 | If the &quot;score&quot; Object uses the &quot;raw&quot; property, the value must be a decimal number between the &quot;min&quot; and &quot;max&quot;, if they are present. If they are not present &quot;raw&quot; can be any number. The LRS rejects with 400 Bad Request a statement with a Result Object using the “raw” property (if it is present) which is not a decimal number or is greater than the value of the “max” property, if it is present, or lesser than the value of the “min” property, if it is present. |
| XAPI-00083 | If the &quot;score&quot; Object uses the &quot;scaled&quot; property, the value must be a decimal number between -1 and 1\. The LRS rejects with 400 Bad Request a statement with a Result Object using the “scaled” property (if it is present) which is not a decimal number or is greater than 1 or less than -1\. |

###  {#-7}

###  {#-8}

###  {#-9}

### 2.4.6. [Context](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#context) {#2-4-6-context}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00084 | A Statement cannot contain both a &quot;revision&quot; property in its &quot;context&quot; property and have the value of the &quot;object&quot; property&#039;s &quot;objectType&quot; be anything but &quot;Activity&quot;. The LRS rejects a statement with 400 Bad Request if contains a &quot;revision&quot; property in its &quot;context&quot; property and does not have an Object with an “objectType” value of “activity” or an Object where the “objectType” property is absent. |
| XAPI-00085 | A Statement cannot contain a &quot;platform&quot; property in its &quot;context&quot; property and have the value of the &quot;object&quot; property&#039;s &quot;objectType&quot; be anything but &quot;Activity&quot;. The LRS rejects a statement with 400 Bad Request if contains a &quot;platform&quot; property in its &quot;context&quot; property and does not have an Object with an “objectType” value of “activity” or an Object where the “objectType” property is absent. |
| XAPI-00086 | A &quot;contextActivities&quot; property is an Object. The LRS rejects with 400 Bad Request a statement with a “contextActivities” property which is not a valid object. |
| XAPI-00087 | A &quot;registration&quot; property is a UUID. The LRS rejects with 400 Bad Request a statement with a “registration” property which is not a valid UUID. |
| XAPI-00087 | An &quot;instructor&quot; property is an Agent. The LRS rejects with 400 Bad Request a statement with an “instructor” property which is not a valid Agent. |
| XAPI-00088 | An &quot;team&quot; property is a Group. The LRS rejects with 400 Bad Request a statement with a “team” property which is not a valid Group. |
| XAPI-00089 | A &quot;revision&quot; property is a String. The LRS rejects with 400 Bad Request a statement with a “revision” property which is not a valid string. |
| XAPI-00090 | A &quot;platform&quot; property is a String. The LRS rejects with 400 Bad Request a statement with a “platform” property which is not a valid string. |
| XAPI-00091 | A &quot;language&quot; property is a String which follows RFC 5646\. The LRS rejects with 400 Bad Request a statement with a “language” property which is not a valid RFC 5646 string. |
| XAPI-00092 | A &quot;statement&quot; property is a Statement Reference. The LRS rejects with 400 Bad Request a statement with a “statement” property which is not a valid StatementRef. |

####  {#-27}

####  {#-28}

####  {#-29}

#### 2.4.6.2 [ContextActivities Property](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#2462-contextactivities-property) {#2-4-6-2-contextactivities-property}

**Definition**

1.  A ContextActivity is defined as a single Activity of the &quot;value&quot; of the &quot;contextActivities&quot; property

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00093 | A &quot;contextActivities&quot; property&#039;s &quot;key&quot; has a value of &quot;parent&quot;, &quot;grouping&quot;, &quot;category&quot;, or &quot;other&quot;. The LRS rejects with 400 Bad Request a statement which has a key other than &quot;parent&quot;, &quot;grouping&quot;, &quot;category&quot;, or &quot;other&quot; for the “contextActivities” property |
| XAPI-00094 | A &quot;contextActivities&quot; property&#039;s &quot;value&quot; is an Activity. The LRS rejects with 400 Bad Request a statement which has a value which is not an Activity for the “contextActivities” property. |
| XAPI-00095 | A &quot;contextActivities&quot; property contains one or more key/value pairs. The LRS rejects with 400 Bad Request a statement which has an empty “contextActivities” property. |
| XAPI-00096 | An LRS&#039;s Statement Resource returns a ContextActivity in an array, even if only a single ContextActivity is returned. |

###  {#-10}

### 2.4.8\. [Stored](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#stored) {#2-4-8-stored}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00097 | An LRS MUST assign the &quot;stored&quot; property timestamp upon receiving a statement. |

###  {#-11}

### 2.4.9. [Authority](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#authority) {#2-4-9-authority}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00098 | An &quot;authority&quot; property which is also a Group contains exactly two Agents. The LRS rejects with 400 Bad Request a statement which has an “authority” property with a “objectType” of “Group” with more or less than two Oauth Agents as values of the “member” property. |
| XAPI-00099 | An LRS populates the &quot;authority&quot; property if it is not provided in the Statement |
| XAPI-00100 | An LRS rejects with error code 400 Bad Request, a Request whose &quot;authority&quot; is a Group having more than two Agents |

###  {#-12}

### 2.4.10. [Version](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#version) {#2-4-10-version}

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00101 | An LRS rejects with error code 400 Bad Request, a Request which uses &quot;version&quot; and has the value set to anything but &quot;1.0&quot; or &quot;1.0.x&quot;, where x is the semantic versioning number |

###  {#-13}

### 2.4.11. [Attachments](https://github.com/adlnet/xAPI-Spec/blob/1.0.3/xAPI-Data.md#attachments) {#2-4-11-attachments}

**Definition**

1.  An Attachment is an Object

**Requirements**

| **ID** | **Requirement** |
| --- | --- |
| XAPI-00102 | A &quot;length&quot; property is an Integer. The LRS rejects with 400 Bad Request a statement which does not have a “length” property or the “length” property is not a valid integer in octets in the Attachment Object. |
| XAPI-00103 | A &quot;sha2&quot; property is a String. The LRS rejects with 400 Bad Request a statement which does not have a “sha2” property or the ”sha2” property is not a valid hash in the Attachment Object. |
| XAPI-00104 | A &quot;fileUrl&quot; property is an IRL. The LRS rejects with 400 Bad Request a statement the “fileURL” property if it is present and it is not a valid IRL in the Attachment Object. |
| XAPI-00105 | A &quot;contentType&quot; property is an Internet Media/MIME type. The LRS rejects with 400 Bad Request a statement which does not have a “contentType” property or the “contentType” property value is not Internet Media/MIME in the Attachment Object. |
| XAPI-00106 | A &quot;display&quot; property is a Language Map. The LRS rejects with 400 Bad Request a statement which does not have a “display” property or the “display” property value is not a valid Language Map in the Attachment Object. |
| XAPI-00107 | A &quot;usageType&quot; property is an IRI. The LRS rejects with 400 Bad Request a statement which does not have a &quot;usageType&quot; property or the &quot;usageType&quot; property value is not a valid IRI in the Attachment Object. |
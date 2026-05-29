The main config file for Consent Blocker.

# Syntax:
* name (string) Name of the CMP or site operator, displayed in the popup and on the blocked page, optional
* comment (string) Short description or comment about the rule (for sake of documentation as json has no comments), optional
* block (boolean) Wherever to block the requests or not, optional
* client (boolean) Set cookies on the client, only uses this if necessary, optional
* disabled (boolean) Disable rule, optional
* cookies (object) Cookies to set/inject, non-strings will be JSON stringified
* storage (object) Nested object (of type "local" or "session") of storage items to set, optional
* types (array) If present only inject the selected webRequest.ResourceType's, optional
* thirdparty (boolean) Inject into 3rd party requests, optional

# Example:
```json
{
    "(www\\.)?example\\.com": {
        "name": "Example",
        "comment": "example rule",
        "client": true,
        "disabled": false,
        "cookies": {
            "string": "string",
            "random": null,
            "int": 1,
            "float": 1.23,
            "boolean": false,
            "object": {"key1":"value1", "key2": 2, "key3": false},
            "array": ["string", 1, 1.23, false]
        },
        "storage": {
            "local": {
                "string": "string",
                "random": null,
                "int": 1,
                "float": 1.23,
                "boolean": false,
                "object": {"key1":"value1", "key2": 2, "key3": false},
                "array": ["string", 1, 1.23, false]
            },
            "session": {
                "string": "string",
                "random": null,
                "int": 1,
                "float": 1.23,
                "boolean": false,
                "object": {"key1":"value1", "key2": 2, "key3": false},
                "array": ["string", 1, 1.23, false]
            }
        },
        "types": ["main_frame"]
    }
}
```
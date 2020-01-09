Validators
===
Validators are used to validate a field and its value in an API response by directly pointing to the position of the field using JSON Path. This way we can entirely skip the arranging of the fields in the object hierarchy for the purpose of validations.

This is particularly useful for service `health-checks` or when we have only a couple of fields or fewer fields to validate in a complex object(`JSON`) structure.

## Field validator
```yaml
---
field: "$.body.type"
value: Premium Visa

or

---
field: "$.body.addresses[0].line1"
value: 164 East Croydon

```

## Block validator

```yaml
---
field: "$.body.location"
value:
  city: Croydon
  country: UK

or

---
field: "$.body.addresses[0]"
value:
  line1: 164 East Croydon
  portcode: EC1 00Y

```

Matchers
===
Matchers are used for validating a number of fields in the API response. Matchers expect the test step to maintain the object hierarchy structure i.e. the arranging of the fields in the object hierarchy for the purpose of validations.

This is particularly useful for full response matching or a subset of the response matching. 
 

## STRICT Matchers
```yaml
---
scenarioName: Validate a GET API
steps:
-     
  ...
  verifyMode: STRICT
  verify:
    body: 
       applicationId:P010203
       visaType: Tier2
```

## LENIENT Matchers
```yaml
---
scenarioName: Validate a GET API
steps:
-     
  ...
  verifyMode: LENIENT
  verify:
    body: 
       visaType: Tier2
```

### Lab Report 2
## Request: `/add-message?s=Hello`
-![Image](add1.png)
- **Methods Called**: `handleRequest`
- **Relevant Arguments**: `url` with value `new URI("/add-message?s=Hello")`
- **Values of Relevant Fields Before Request**: 
  - Assuming this is the first request and no other messages have been added, `messages` = `[]` (an empty list).
- **How Values Change**: 
  - The `messages` list gets updated to `["1. Hello"]`




* The basis fundamental idea is that spec should drive the application.
* Say we write spec (eg a swagger spec) of a server.
* It already has the request payload schema, and hence most part of corresponding model schema.
  * No need to explicitly define again that model schema in code. 
  * Use the spec schema and modify if required to have abstraction from outer world
* It already has the routes, and method
  * Map `operationId` with the corresponding handler name.
  * Write a simple startup script that reads spec and define routes and map endpoint-method with the handler which is defined as `operationId` in spec.
* It already has sample error codes or messages or some default success code and messages.
  * Don't hadcode error responses, rather use the spec to generate error responses / default success code and messages.
* Keep the application data driven when data is stored in spec.
  

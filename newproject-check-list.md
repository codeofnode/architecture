* First of all is organized.
  * Purely OOP based.
  * And yet with microservices (not really, but of similar fashion) approach.
* Make plugin based architecture:
  * Make a base of application, that support features based on plugins. So that removing and adding of plugin should be smooth.
* Sticking with pure node, as much as possible. (dont even use even express or hapi)
  * Using async await is a great boon, with new javascript. So why fibers?
* Should use event based system, wherever needed
* Always use a wrapper for all kind of basic services, like db communcation, logging, So that things like changing db, should be just plug and play
* Linting
* Testing of various units
* Code coverage.
* Easily scalable to n number of nodes, make it stateless.
* Easy migration or database
* Easy to  Ship - We can make a single lightweight binary to deploy as microservice.

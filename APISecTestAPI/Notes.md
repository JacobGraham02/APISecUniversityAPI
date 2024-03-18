OWASP #1: Broken Object Level Authorization
	Allows an object from a request to be authorized as another object. For example, if two users are using a service, a Broken Object Level
Authorization vulnerability will allow a request from user A to act as a request from user B

OWASP #2: Broken Authentication
	Allows any user to use an API endpoint and access all of the data within the system that the API has access to. This can be caused by authentication not being in place or
authentication being in place, but authorization not being in place. 

OWASP #3: Broken Object Property Level Authorization
	Excessive data exposure when using an API. For example, when using an API endpoint, a user can expose not only their anonymous data, but the data of all users.

OWASP #4: Unrestricted Resource Consumption
	Unrestricted access to very large amounts of data, generally by not specifying API limits on querying data. An example of this is Venmo, where hackers could query
limitless (115,000) transactions per day from the API, harvesting a total of 207 million over time. 

OWASP #5: Broken Function Level Authentication
	Functions like CRUD (Create, Read, Update, Delete) which are available to end users when using a(n) API endpoint. 
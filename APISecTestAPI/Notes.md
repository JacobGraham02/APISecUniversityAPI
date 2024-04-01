Example API security issues:
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

OWASP top 10 background:
	1. Broken object level authorization
		Manipulation of APIs to access data/objects belonging to other users. Can lead to data loss, disclosure, and data manipulation. Attacker authencates as User A 
		and then retrieves data on User B. Need to ensure no data bleeds across entities
		You can prevent this by:
			Defining data acess policies and implement associated controls
			Enforce data access controls at application logic layer
			Implement automated testing to find BOLA laws

	2. Broken authentication
		Weak or poor authentication creates vulnerability: 
			Missing security controls or poorly implemented controls. Can expose account takeover risks, data theft, or unauthorized transactions. 
		You can prevent this by:
			Define authentication policies and standards; follow best practices
			Implement continuous testing

	3. Broken object property level authorization
		Exploit of endpoints by reading and/or modifying values of objects. Ability to update object elements ("mass assignment"). Revealing unnecessary sensitive data 
		("excessive data exposure"). User is able to set "account-type=premium". User search endpoint returns excessive, unnecessary details (name, email, address, ID, ...)
		You can prevent this by:
			Ensure user can only access legitimate, permitted fields
			Return only minimum amount of data required for the use case.

	4. Unrestricted resource consumption
		Abuse of APIs due to high volumes of API calls, large requests, etc. Denial of service, performance impact, and mass data harvesting.
		Examples include missing/inadqeuate rate controls, execution timeouts, max allocable memory, max number of files and upload size, etc.
		You can prevent this by:
			Implement traffic controls
			Test effectiveness of controls

	5. Broken function level authorization
		Abuse of API functionality to improperly modify objects (create, update, delete)
		Often involves replacing passive methods (GET) with active (PUT, DELETE). May be used to escalate privileges and can be exploited to modify account details
		Examples include: modify parameters - "role = admin", deleting an invoice, and set account balance = $0
		You can prevent this by:
			Indentify functions that expose high sensitivty capability and develop controls to limit access
			Implement continuous release testing to ensure proper behavior

	6. Unrestricted access to sensitive business flows
		Abuse of a legitimate business workflow through excessive, automated use. Rate limiting, captchas not always effective against fradulent traffic. Rapid IP rotation
		makes detection difficult. Typically a result of application logic flaw. Loss of critical business activity. Examples include:
	7. Server side request forgery
	8. Security misconfiguration
	9. Improper inventory management
	10. Unsafe consumption of APIs


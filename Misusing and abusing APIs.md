# Misusing and abusing APIs
- Keith Casey
- Kin lane
	-  Api evangalist
-  Assumptions
	-  Everyone is working with APIs
		-  Use them on a regular basis
		-  Potentially build them too
		-  Sometimes public, sometimes private
	-  nothing is perfect
		-  you make mistakes
		-  your providers make mistakes
		-  that other team are all knuckleheads
		-  Your team is great
-  What I'm not going to cover
	-  Cambridge Analytica
		-  not a data breach, not even misuse
	-  currently open vulnerabilities
	-  specific hacking tools and methods
-  Examples
	-  Equifax
	-  FourSquare
		-  robmyhouse.com
		-  kind of dated
		-  facebook has places
	- Voice/SMS Providers
		- Great for social networking
		- compromise voice mail
		- denial of service
	- Api side
		- `curl -X POST http://api.company.com/sms?key=abcdefg`
			- `-d "Body=Hello%20World` 
			- `-d "To=15128675309"`
			- `-d "From=17192662857"`
	- Panera
		- completely unprotected api
		- reported in august 2017 not addressed until april 2018
		- give access to name, address, email, username, phone, birthday, food preferences, and last 4 credit card digits
	- Equifax
		- 
-  What can we do?
	-  If you're not encrypting data in flight, its already lost.
	-  Malicious, naive, and incompetent look the same
	-  Authentication vs Authorization
		-  authentication is who you are.
		-  authorization is what you are allowed to do.
	-  Key and token management
		-  dont embed in url
		-  key should not have access to everything
		-  expire and rotate keys
		-  provide multiple keys
		-  understand the use cases youre addressing
		-  scope your api keys
	- WRITE GOOD EXAMPLES
		-   what does sample code demonstrate
			- what the api does
			- how to use the api
			- the right way to use the api
-  What should we avoid?
	-  dont roll you own encryption
		-  use an existing library that implements an open standadrd, audit if you prefer
		-  dont creat your own
		-  no youre not special
	-  dont leak your own data
		-  do the urls tell a story
		-  does that put customers at risk
	-  dont collect and share extra data
		-  why should people
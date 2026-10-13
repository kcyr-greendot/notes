**October 09, 2026**
JH: Connie Ching, Jim Johnson, Tom Salisbury
Green Dot: Ray, Tony W

- questions around 3rd party technical integrations 
- Connie is running the RFP; Tom - leads application development; Jimmy - technology service partner (liaison between business and tech team)
- test environments - JH has four test environments
	- dev - devs active working
	- test - QA testing
	- staging - pre-prod
	- prod 
- we do have vendors that don't support all four environments but we run into progress in our development cycles 
- Tony: we have two lower environments (Sandbox and PIE)
	- your process is standard SDLC and we embrace that approach 
	- webhooks are challenging - how to get them across environments 
- Tom - "I would not push for a 1:1 match for each environment"
- Jim - can we match sandbox to dev & sandbox; match staging to PIE? 
	- Tony - makes sense, we may be able to customize a sandbox for your program's needs
- Jim: what about load & performance testing? 
	- Tony: we do our own internal performance testing - can we coordinate and do the testing ourselves? we don't have a partner-facing environment for performance testing
	- Tom: not ideal, how can we validate that you have done this testing to our specific needs? concerned about failures at the integration layer
	- Tony: perf environment doesn't have customer specifications; we could temporarily scale up PIE to match production environment scale 
- maintenance windows: 
	- "a day at Jackson Hewitt is like a week at another company"
	- we have a very short window to make all of our revenue
	- vendors who didn't honor our maintenance windows... and even unrelated features have burned us in the past
	- Tony: what are the windows?
		  General Deployment restriction periods:
			- January 15 – February 25
			- April 05 – April 20
			- October 10 – October 20
			- December 01 – December 24
		- Dec 1 - start of tax season (early refund advance)
		- Jan 15 - Feb 25 - IRS starts processing returns and PATH funding comes back from IRS
		- April 5-April 20 - tax filing deadlines
	- what is level of tolerance for impact?
		- we will deploy during those windows very sparingly, 2 - 3 AM 
		- it's not a zero tolerance policy but we have it absolutely minimally 
		- we want to have the conversation - we approach it like a "risk management period"
	- we do daily deployments - but it's night time (9 PM - 2 AM Pacific) Sunday - Wednesday 
		- close to zero downtime
	- we do have a single tenant option if it's absolutely needed - and can have full control separate from the general environment
	- Tom - "a single tenant environment would make me so happy" - would be the ideal solution 
	- 
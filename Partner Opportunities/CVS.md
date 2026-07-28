**July 27, 2026**
[Angeline, Srikala, Taylor, Mani, Michelle]

- Veronica took over as PM
- 5 items for CVS to deploy Phase 1 (pre-auth)
	- as we went through that list - we discovered some things that didn't align with expectations 

![[Screenshot 2026-07-27 at 3.35.33 PM.png]]

- explaining the "hybrid solution"
	- PIE is connected to QA3 but partner is integrated to QA4 (which will never work - they never should have been granted access to this)
	- hybrid solution - using POS and 1.0 API together 
	- Mani and Sean meeting this afternoon to go over it in more details
- current goal is to be in Production with pre-auth 
- don't need new test cases on ISO 8583 - that's already live and working
- we haven't done 2.0 pre-auth yet - they're testing on 1.0 API version 
- Phase 1 - pre-auth to 2.0 (azure) API first 
	- if auth succeeeds- go to ISO 8583 operation
	- if auth declines, do nothing
- Phase 2 - adding Swipe Reloads 
- Sean is concerned about the volume of the testing that is needed 
- -[ ] Taylor committing to sending docs to CVS by eOD Thursday

**July 23, 2026** 
[Angeline, Mani, Sean, Michelle, Kevin, Srikala, Lee, Chrissy]

- we're stuck on connectivity challenges with CVS
- they're using teh wrong instance for testing (QA4 vs. QA3)
- we're not sure why ... Mani is frustrated by this 
AUTOMATED TEST SUITE NAME: demoblaze-automation

GITHUB URL: https://github.com/saranyamurthy/demoblaze-automation

AUTHOR: Saranya Murthy (GitHub username: saranyamurthy)

DATE CREATED: July 7, 2021

EXECUTIVE SUMMARY
-----------------
15 TEST RUNS
4 FAILURES
4 DEFECTS

CONTENTS
--------
demoblaze-automation.side

PURPOSE
-------
The goal of this test suite is to automate the following areas of coverage requested by the client for the 'demoblaze' web site (https://www.demoblaze.com/index.html):

1) Account creation
2) Log in
3) Browsing the store's main categories (Phones, Laptops, Monitors0
4) Searching for phones
5) Play "About Us" video
6) Shopping cart and Checkout

STATUS
------
Four out of six areas were successfully automated

- Log in
- Browsing the store's main categories (Phones, Laptops, Monitors
- Searching for phones (automated for a different site, since the 'demoblaze' web site does not have this functionality implemented yet)
- Shopping cart and checkout

I recommend that the remaining two areas be tested manually

- Account creation
- Play "About Us" video

JUSTIFICATION
-------------
In order to maximize the automated test coverage within the given timeframe of 8 hours, I chose Selenium IDE to implement the automated tests. It was a straightforward record-and-playback tool. 

I discovered that Selenium IDE had certain limitations:

1) the inability to generate random strings of numbers and letters
2) the inability to record the playing of embedded videos

Due to Limitation 1), account creation could not be automated. Recording the creation of a specific set of credentials implies that the same set of credentials cannot be re-used for future test runs because the user already exists in the system and cannot be created a second time.

Due to Limitation 2), the Play "About Us" video test could not be automated. I recorded my actions but the video did not play when the test was run and the test failed (false negative).

I researched ways to accomplish the desired goal and have recorded my findings in the following tests. For now, I recommend testing the following areas manually since the cost of creating a manual test with a new tool other than Selenium IDE outweighs the benefits of having these areas automated:

1) Create Account - INCOMPLETE - MANUAL TEST ONLY. Functional happy-path test is expected to take 1-5 minutes.
2) Play "About Us" video - INCOMPLETE - MANUAL ONLY. Functional happy-path test is the length of the video. It is unlikely (although not impossible) that changes to the web site will break the video. If this happens, the failure can be detected as soon as the QA Analyst attempts to play the video.

ORDER OF TESTS
---------------
The 6 tests can be run in any order.

WHAT WOULD I DO DIFFERENTLY NEXT TIME
-------------------------------------
Select a different tool, such as Selenium Web Driver. Learn how to use it prior to beginning client engagement. Confirm that it can utilize JavaScript to generate random strings and record the playing of embedded videos.

Select a tool that allows validation of popup content. A limitation of Selenium IDE is that it fails on 'assertAlerts' so the QA Team cannot use this tool to determine whether valid message content ("Please fill out Username and Password") was displayed.

9 OPTIONAL TESTS
----------------
The following 9 optional tests have been added to the suite. These are outside of the coverage the client specifically requested. I consider them value-adding tests:

1) Attempt to submit empty forms - FAIL
2) Click through images using Front and Back Arrows - PASS
3) Clickable Icons (Logo, Store, Home) - PASS
4) Close various dialogs - PASS
5) Contact - Send a Message - FAIL
6) Incorrect Password - PASS
7) Log Out - FAIL
8) Non-existent Username - FAIL
9) Purchase >1 Item - PASS

4 DEFECTS
---------
1) linkText for Phones reads Laptops instead of Phones. See "linkText Issue for future investigation" folder for details
2) Purchase Date is incorrect when you place an order. It reads July 6th 2021. The expected date is today's date (July 7th 2021). See "High Level Defects" folder for details (Issue 2.png).
3) Carousel Indicators do not have any effect on individual images. Click on "Phones" -> "Nokia Lumia 1520". See "High Level Defects" folder for details (Issue 3.png).
4) The "Place Order" button is enabled for an empty cart. When the customer clicks it, no error message is shown. Customers should not be able to place empty orders since this action will have no meaningful result for the end user. See "High Level Defects" folder for details (Issue 4.png and Issue 4 Part 2.png).
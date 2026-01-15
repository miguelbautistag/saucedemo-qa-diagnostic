# 🕵️‍♂️ Sauce Demo - QA Diagnostic & Bug Tracking

## 📌 Project Overview
This project consists of a deep-dive functional analysis of the [Sauce Demo](https://www.saucedemo.com/) e-commerce platform. The goal was to identify critical functional gaps using the **'error_user'** profile and document them following industry standards.

## 🛠️ Tools Used
- **Jira:** Defect management and bug lifecycle tracking.
- **Google Sheets:** Test case design and execution.
- **Chrome DevTools:** Console error analysis and network inspection.

## 📋 Test Artifacts
- **Test Cases:**
ID,Description,Preconditions,Steps,Test Data,Expected Result,Status,Bug ID
TC001,Verify login doesn't work with blank fields,Access https://www.saucedemo.com/,1. Click on login,N/A,"Message: ""Username is required""",Passed,
TC002,"Verify ""username"" field accepts new data",Access https://www.saucedemo.com/,"1. Click on ""username""
2. Write down ""standard_user""",N/A,The field displays the entered characters correctly and maintains focus,Passed,
TC003,"Verify ""password"" field accepts new data",Access https://www.saucedemo.com/,"1. Click on ""password""
2. Write down ""secret_sauce""",N/A,The field displays the entered characters correctly and maintains focus,Passed,
TC004,Verify login works when a correct username and password is used,Access https://www.saucedemo.com/,"1. Click on ""username"" and write a correct username
2. Click on ""password"" and write a correct password
3. Click on ""Login""","Username: standard_user
Password: secret_sauce",User can login and see Swag Labs products,Passed,
TC005,Verify login doesn't work when an incorrect username and password is used,Access https://www.saucedemo.com/,"1. Click on ""username"" and write an incorrect username
2. Click on ""password"" and write an incorrect password
3. Click on ""Login""","Username: standard_user1
Password: secret_sauce1",Message: Username and Password do not match any user in this service,Passed,
TC006,Verify login doesn't work when a correct username and incorrect password is used,Access https://www.saucedemo.com/,"1. Click on ""username"" and write a correct username
2. Click on ""password"" and write an incorrect password
3. Click on ""Login""","Username: standard_user
Password: secret_sauce1",Message: Username and Password do not match any user in this service,Passed,
TC007,Verify login doesn't work when an incorrect username and correct password is used,Access https://www.saucedemo.com/,"1. Click on ""username"" and write an incorrect username
2. Click on ""password"" and write a correct password
3. Click on ""Login""","Username: standard_user1
Password: secret_sauce",Message: Username and Password do not match any user in this service,Passed,
TC008,Verify message when a user is locked out ,Access https://www.saucedemo.com/,"1. Click on ""username"" and write ""locked_out_user"" which simulates a locked out user
2. Click on ""password"" and write a correct password
3. Click on ""Login""","Username: locked_out_user
Password: secret_sauce","Message: Sorry, this user has been locked out",Passed,
TC009,"Verify the ""add to cart"" button works for item ""Sauce Labs Backpack""","Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Click on ""add to cart"" for item ""Sauce Labs Backpack""","Username: standard_user
Password: secret_sauce","""Sauce Labs Backpack"" added to cart and ""add to cart"" button changes to ""remove""",Passed,
TC010,Verify an item can be removed from the cart,"Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Click on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""remove"" for ""Sauce Labs BackPack""","Username: standard_user
Password: secret_sauce",Item removed from the cart,Passed,
TC011,Verify an item can be removed from inventory page,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials","1. Click on ""add to cart"" for item ""Sauce Labs Backpack""
2. Confirm ""add to cart"" button was changed for ""removed""
3. Click on ""remove"" button","Username: error_user
Password: secret_sauce","When clicking on ""remove"", item is removed and button changes to ""add to cart""",Failed,SDT-1
TC012,Verify filters work on inventory page,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials","1. Click on filter option
2. Select ""Name (A to Z)""","Username: error_user
Password: secret_sauce",Products are filtered from A to Z,Failed,SDT-3
TC013,"Verify filter ""Price (High to low)"" works","Access https://www.saucedemo.com/

User is logged in with ""visual_user"" credentials","1. Click on filter option
2. Select ""Price (High to low)""","Username: visual_user
Password: secret_sauce",Products are filtered from High to low price,Failed,SDT-3
TC014,"Verify image for ""Sauce Labs Backpack"" corresponds to the item","Access https://www.saucedemo.com/

User is logged in with ""visual_user"" credentials","1. Check image on inventory page for ""Suace Labs Backpack""","Username: visual_user
Password: secret_sauce","Image for ""Sauce Labs Backpack"" corresponds to the item",Failed,SDT-4
TC015,"Verify price for ""Sauce Labs BIke Light"" matches the one in inventory page vs the price inside the item itself ","Access https://www.saucedemo.com/

User is logged in with ""visual_user"" credentials","1. Verify price in inventory page for ""Sauce labs bike light""
2. Click on ""Sauce labs bike light""
3. Confirm price matches","Username: visual_user
Password: secret_sauce","Prices on inventory page for ""Sauce labs bike light"" vs the price in the item itself are the same",Failed,SDT-5
TC016,Verify user can checkout an item from the cart,"Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""","Username: standard_user
Password: secret_sauce","User taken to ""checkout"" screen""",Passed,
TC017,"Verify checkout doesn't work if ""first name, last name and zip code"" is blank","Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Click on ""Continue""","Username: standard_user
Password: secret_sauce","Message: ""Error: First Name is required""",Passed,
TC018,"Verify checkout doesn't work if ""first name"" is filled but ""last name and zip code"" is blank","Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Fill ""First name""
4. Click on ""Continue""","Username: standard_user
Password: secret_sauce

First Name: ""MIguel""","Message: ""Error: Last Name is required""",Passed,
TC019,"Verify checkout doesn't work if ""first name"" and ""last name"" is filled but ""zip code"" is blank","Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Fill ""First name"" and ""Last name""
4. Click on ""Continue""","Username: standard_user
Password: secret_sauce

First Name: ""MIguel""
Last Name: ""Bautista""","Message: ""Error: Postal code is required""",Passed,
TC020,Verify checkout works when all fields are filled,"Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Fill ""First name"", ""Last name"" and ""Postal Code""
4. Click on ""Continue""","Username: standard_user
Password: secret_sauce

First Name: ""MIguel""
Last Name: ""Bautista""
Postal Code: ""5035""","User can see the ""checkout overview"" screen",Passed,
TC021,"Verify checkout is completed when clicking on ""finish""","Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Fill ""First name"", ""Last name"" and ""Postal Code""
4. Click on ""Continue""
5. Clikc on ""Finish""","Username: standard_user
Password: secret_sauce

First Name: ""MIguel""
Last Name: ""Bautista""
Postal Code: ""5035""","User can see the ""checkout overview"" screen",Passed,
TC022,Verify checkout can be cancelled,"Access https://www.saucedemo.com/

User is logged in with ""standard_user"" credentials","1. Cick on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on the ""cart"", then click on ""Checkout""
3. Fill ""First name"", ""Last name"" and ""Postal Code""
4. Click on ""Continue""
5. Clikc on ""Cancel""","Username: standard_user
Password: secret_sauce

First Name: ""MIguel""
Last Name: ""Bautista""
Postal Code: ""5035""",User cancels the checkout and is taken to the home screen,Passed,

- **Bug Reports:**
Bug ID,Title,Description,Environment,Previous Conditions,Steps to Reproduce,Expected Result,Actual Result,Severity,Priority
BG001,Items cannot be removed from inventory page,"When clicking on ""remove"" from inventory page items are not removed",Chrome v120.0.6099,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials and password ""secret_sauce""","1. Click on ""add to cart"" for item ""Sauce Labs Backpack""
2. Click on ""remove"" button","When clicking on ""remove"", item is removed and button changes to ""add to cart""","When clicking on ""remove"" from inventory page items are not removed",Major,High
BG002,Filters do not work from inventory page,An error is shown when flitering from inventory page,Chrome v120.0.6099,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials and password ""secret_sauce""","1. Click on filter option
2. Select ""Name (A to Z)""",Products are filtered from A to Z,"Error message ""Sorting is broken! This error has been reported to Backtrace""",Major,Medium
BG003,"Filter ""Price (High to low)"" doesn't work","When filtering ""Price (High to low)"" items are filtered randomly",Chrome v120.0.6099,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials and password ""secret_sauce""","1. Click on filter option
2. Select ""Price (High to low)""",Products are filtered from High to low price,"When filtering ""Price (High to low)"" items are filtered randomly",Major,High
BG004,"Image for ""Sauce Labs Backpack"" doesn't correspond to the item","Image for ""Sauce Labs Backpack"" shows a dog instead of a bag",Chrome v120.0.6099,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials and password ""secret_sauce""","1. Check image on inventory page for ""Sauce Labs Backpack""","Image for ""Sauce Labs Backpack"" corresponds to the item","Image for ""Sauce Labs Backpack"" shows a dog instead of a bag",Major,High
BG005,"Price for ""Sauce Labs BIke Light"" doesn't match","Price for ""Sauce Labs BIke Light"" doesn't match the one in inventory page vs the price inside the item itself ",Chrome v120.0.6099,"Access https://www.saucedemo.com/

User is logged in with ""error_user"" credentials and password ""secret_sauce""","1. Verify price in inventory page for ""Sauce labs bike light""
2. Click on ""Sauce labs bike light""
3. Confirm price matches","Prices on inventory page for ""Sauce labs bike light"" vs the price in the item itself are the same ($9.99)","Price for ""Sauce Labs BIke Light"" doesn't match the one in inventory page ($80.72) vs the price inside the item itself ($9.99)

",Major,High

## 📊 Jira Lifecycle Management
I managed the identified bugs through a standard Kanban workflow in Jira.

### Kanban Board View
<img width="1362" height="311" alt="jira-board" src="https://github.com/user-attachments/assets/c92f7a20-11c1-46cd-8511-b485b8f25d8c" />


### Sample Bug Report (Jira Detail)
<img width="877" height="762" alt="Bug-detail" src="https://github.com/user-attachments/assets/f10920d7-65e7-4117-be7f-d7cfda8512da" />


## 🎯 Key Findings
- Found **5 high-priority defects** affecting core business logic (Pricing, Cart Management, and Filtering).
- Identified visual regressions and data mapping errors using the 'error_user' credential.

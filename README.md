# 🕵️‍♂️ Sauce Demo - QA Diagnostic & Bug Tracking

## 📌 Project Overview
This project consists of a deep-dive functional analysis of the [Sauce Demo](https://www.saucedemo.com/) e-commerce platform. The goal was to identify critical functional gaps using the **'error_user'** profile and document them following industry standards.

## 🛠️ Tools Used
- **Jira:** Defect management and bug lifecycle tracking.
- **Google Sheets:** Test case design and execution.
- **Chrome DevTools:** Console error analysis and network inspection.

## 📋 Test Artifacts
- **Test Cases:**

<details> <summary><b>Click to expand Test Cases (TC001 - TC022)</b></summary>
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

- **Bug Reports:**
<details><summary><b>Click to expand Bug Reports (BG001 - BG005)</b></summary>Bug IDTitleEnvironmentSeverityPriorityActual ResultBG001Items cannot be removedChrome v120🔴 Major⚡ HighRemove button does not trigger actionBG002Filters crashChrome v120🔴 Major🟠 MediumError: "Sorting is broken!"BG003Price Filter logicChrome v120🔴 Major⚡ HighItems filtered in random orderBG004Image MismatchChrome v120🔴 Major⚡ HighShows a dog instead of a backpackBG005Price DiscrepancyChrome v120🔴 Major⚡ HighList ($80.72) vs Detail ($9.99)

## 📊 Jira Lifecycle Management
I managed the identified bugs through a standard Kanban workflow in Jira.

### Kanban Board View
<img width="1362" height="311" alt="jira-board" src="https://github.com/user-attachments/assets/c92f7a20-11c1-46cd-8511-b485b8f25d8c" />


### Sample Bug Report (Jira Detail)
<img width="877" height="762" alt="Bug-detail" src="https://github.com/user-attachments/assets/f10920d7-65e7-4117-be7f-d7cfda8512da" />


## 🎯 Key Findings
- Found **5 high-priority defects** affecting core business logic (Pricing, Cart Management, and Filtering).
- Identified visual regressions and data mapping errors using the 'error_user' credential.

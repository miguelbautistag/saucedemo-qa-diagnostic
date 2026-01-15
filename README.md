# 🕵️‍♂️ Sauce Demo - QA Diagnostic & Bug Tracking

## 📌 Project Overview
This project consists of a deep-dive functional analysis of the [Sauce Demo](https://www.saucedemo.com/) e-commerce platform. The goal was to identify critical functional gaps using the **'error_user'** profile and document them following industry standards.

## 🛠️ Tools Used
- **Jira:** Defect management and bug lifecycle tracking.
- **Google Sheets:** Test case design and execution.
- **Chrome DevTools:** Console error analysis and network inspection.

## 📋 Test Artifacts
- **Test Cases:**
<table>
    <tr>
        <td>ID</td>
        <td>Description</td>
        <td>Preconditions</td>
        <td>Steps</td>
        <td>Test Data</td>
        <td>Expected Result</td>
        <td>Status</td>
        <td>Bug ID</td>
    </tr>
    <tr>
        <td>TC001</td>
        <td>Verify login doesn&#39;t work with blank fields</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on login</td>
        <td>N/A</td>
        <td>Message: &quot;Username is required&quot;</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC002</td>
        <td>Verify &quot;username&quot; field accepts new data</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Write down &quot;&quot;standard_user&quot;&quot;&quot;</td>
        <td>N/A</td>
        <td>The field displays the entered characters correctly and maintains focus</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC003</td>
        <td>Verify &quot;password&quot; field accepts new data</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;password&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Write down &quot;&quot;secret_sauce&quot;&quot;&quot;</td>
        <td>N/A</td>
        <td>The field displays the entered characters correctly and maintains focus</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC004</td>
        <td>Verify login works when a correct username and password is used</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;&quot; and write a correct username<br>2. Click on &quot;&quot;password&quot;&quot; and write a correct password<br>3. Click on &quot;&quot;Login&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce</td>
        <td>User can login and see Swag Labs products</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC005</td>
        <td>Verify login doesn&#39;t work when an incorrect username and password is used</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;&quot; and write an incorrect username<br>2. Click on &quot;&quot;password&quot;&quot; and write an incorrect password<br>3. Click on &quot;&quot;Login&quot;&quot;</td>
        <td>Username: standard_user1<br>Password: secret_sauce1</td>
        <td>Message: Username and Password do not match any user in this service</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC006</td>
        <td>Verify login doesn&#39;t work when a correct username and incorrect password is used</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;&quot; and write a correct username<br>2. Click on &quot;&quot;password&quot;&quot; and write an incorrect password<br>3. Click on &quot;&quot;Login&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce1</td>
        <td>Message: Username and Password do not match any user in this service</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC007</td>
        <td>Verify login doesn&#39;t work when an incorrect username and correct password is used</td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;&quot; and write an incorrect username<br>2. Click on &quot;&quot;password&quot;&quot; and write a correct password<br>3. Click on &quot;&quot;Login&quot;&quot;</td>
        <td>Username: standard_user1<br>Password: secret_sauce</td>
        <td>Message: Username and Password do not match any user in this service</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC008</td>
        <td>Verify message when a user is locked out </td>
        <td>Access https://www.saucedemo.com/</td>
        <td>1. Click on &quot;&quot;username&quot;&quot; and write &quot;&quot;locked_out_user&quot;&quot; which simulates a locked out user<br>2. Click on &quot;&quot;password&quot;&quot; and write a correct password<br>3. Click on &quot;&quot;Login&quot;&quot;</td>
        <td>Username: locked_out_user<br>Password: secret_sauce</td>
        <td>Message: Sorry, this user has been locked out</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC009</td>
        <td>Verify the &quot;add to cart&quot; button works for item &quot;Sauce Labs Backpack&quot;</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Click on &quot;add to cart&quot; for item &quot;Sauce Labs Backpack&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce</td>
        <td>Sauce Labs Backpack&quot; added to cart and &quot;add to cart&quot; button changes to &quot;remove</td>
        <td>Passed</td>
        <td></td>
    </tr>
    <tr>
        <td>TC010</td>
        <td>Verify an item can be removed from the cart</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Click on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;remove&quot;&quot; for &quot;&quot;Sauce Labs BackPack&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce</td>
        <td>Item removed from the cart</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC011</td>
        <td>Verify an item can be removed from inventory page</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials</td>
        <td>1. Click on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Confirm &quot;&quot;add to cart&quot;&quot; button was changed for &quot;&quot;removed&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Click on &quot;&quot;remove&quot;&quot; button&quot;</td>
        <td>Username: error_user<br>Password: secret_sauce</td>
        <td>When clicking on &quot;remove&quot;, item is removed and button changes to &quot;add to cart&quot;</td>
        <td>Failed</td>
        <td>SDT-1</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC012</td>
        <td>Verify filters work on inventory page</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials</td>
        <td>1. Click on filter option<br>2. Select &quot;&quot;Name (A to Z)&quot;&quot;</td>
        <td>Username: error_user<br>Password: secret_sauce</td>
        <td>Products are filtered from A to Z</td>
        <td>Failed</td>
        <td>SDT-3</td>
    </tr>
    <tr>
        <td>TC013</td>
        <td>Verify filter &quot;Price (High to low)&quot; works</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;visual_user&quot;&quot; credentials</td>
        <td>1. Click on filter option<br>2. Select &quot;&quot;Price (High to low)&quot;&quot;</td>
        <td>Username: visual_user<br>Password: secret_sauce</td>
        <td>Products are filtered from High to low price</td>
        <td>Failed</td>
        <td>SDT-3</td>
    </tr>
    <tr>
        <td>TC014</td>
        <td>Verify image for &quot;Sauce Labs Backpack&quot; corresponds to the item</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;visual_user&quot;&quot; credentials</td>
        <td>1. Check image on inventory page for &quot;Suace Labs Backpack&quot;</td>
        <td>Username: visual_user<br>Password: secret_sauce</td>
        <td>Image for &quot;Sauce Labs Backpack&quot; corresponds to the item</td>
        <td>Failed</td>
        <td>SDT-4</td>
    </tr>
    <tr>
        <td>TC015</td>
        <td>Verify price for &quot;Sauce Labs BIke Light&quot; matches the one in inventory page vs the price inside the item itself </td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;visual_user&quot;&quot; credentials</td>
        <td>1. Verify price in inventory page for &quot;&quot;Sauce labs bike light&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on &quot;&quot;Sauce labs bike light&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Confirm price matches&quot;</td>
        <td>Username: visual_user<br>Password: secret_sauce</td>
        <td>Prices on inventory page for &quot;Sauce labs bike light&quot; vs the price in the item itself are the same</td>
        <td>Failed</td>
        <td>SDT-5</td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC016</td>
        <td>Verify user can checkout an item from the cart</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce</td>
        <td>User taken to &quot;checkout&quot; screen&quot;</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC017</td>
        <td>Verify checkout doesn&#39;t work if &quot;first name, last name and zip code&quot; is blank</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Click on &quot;&quot;Continue&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce</td>
        <td>Message: &quot;Error: First Name is required&quot;</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC018</td>
        <td>Verify checkout doesn&#39;t work if &quot;first name&quot; is filled but &quot;last name and zip code&quot; is blank</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Fill &quot;&quot;First name&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4. Click on &quot;&quot;Continue&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce<br>First Name: &quot;&quot;MIguel&quot;&quot;</td>
        <td>Message: &quot;Error: Last Name is required&quot;</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC019</td>
        <td>Verify checkout doesn&#39;t work if &quot;first name&quot; and &quot;last name&quot; is filled but &quot;zip code&quot; is blank</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Fill &quot;&quot;First name&quot;&quot; and &quot;&quot;Last name&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4. Click on &quot;&quot;Continue&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce<br>First Name: &quot;&quot;MIguel&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Last Name: &quot;&quot;Bautista&quot;&quot;&quot;</td>
        <td>Message: &quot;Error: Postal code is required&quot;</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC020</td>
        <td>Verify checkout works when all fields are filled</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Fill &quot;&quot;First name&quot;&quot;, &quot;&quot;Last name&quot;&quot; and &quot;&quot;Postal Code&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4. Click on &quot;&quot;Continue&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce<br>First Name: &quot;&quot;MIguel&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Last Name: &quot;&quot;Bautista&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Postal Code: &quot;&quot;5035&quot;&quot;&quot;</td>
        <td>User can see the &quot;checkout overview&quot; screen</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC021</td>
        <td>Verify checkout is completed when clicking on &quot;finish&quot;</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Fill &quot;&quot;First name&quot;&quot;, &quot;&quot;Last name&quot;&quot; and &quot;&quot;Postal Code&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4. Click on &quot;&quot;Continue&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>5. Clikc on &quot;&quot;Finish&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce<br>First Name: &quot;&quot;MIguel&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Last Name: &quot;&quot;Bautista&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Postal Code: &quot;&quot;5035&quot;&quot;&quot;</td>
        <td>User can see the &quot;checkout overview&quot; screen</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>TC022</td>
        <td>Verify checkout can be cancelled</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;standard_user&quot;&quot; credentials</td>
        <td>1. Cick on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on the &quot;&quot;cart&quot;&quot;, then click on &quot;&quot;Checkout&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Fill &quot;&quot;First name&quot;&quot;, &quot;&quot;Last name&quot;&quot; and &quot;&quot;Postal Code&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>4. Click on &quot;&quot;Continue&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>5. Clikc on &quot;&quot;Cancel&quot;&quot;&quot;</td>
        <td>Username: standard_user<br>Password: secret_sauce<br>First Name: &quot;&quot;MIguel&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Last Name: &quot;&quot;Bautista&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>Postal Code: &quot;&quot;5035&quot;&quot;&quot;</td>
        <td>User cancels the checkout and is taken to the home screen</td>
        <td>Passed</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>

- **Bug Reports:**
<table>
    <tr>
        <td>Bug ID</td>
        <td>Title</td>
        <td>Description</td>
        <td>Environment</td>
        <td>Previous Conditions</td>
        <td>Steps to Reproduce</td>
        <td>Expected Result</td>
        <td>Actual Result</td>
        <td>Severity</td>
        <td>Priority</td>
    </tr>
    <tr>
        <td>BG001</td>
        <td>Items cannot be removed from inventory page</td>
        <td>When clicking on &quot;remove&quot; from inventory page items are not removed</td>
        <td>Chrome v120.0.6099</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials and password &quot;&quot;secret_sauce&quot;&quot;</td>
        <td>1. Click on &quot;&quot;add to cart&quot;&quot; for item &quot;&quot;Sauce Labs Backpack&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on &quot;&quot;remove&quot;&quot; button&quot;</td>
        <td>When clicking on &quot;remove&quot;, item is removed and button changes to &quot;add to cart&quot;</td>
        <td>When clicking on &quot;remove&quot; from inventory page items are not removed</td>
        <td>Major</td>
        <td>High</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>BG002</td>
        <td>Filters do not work from inventory page</td>
        <td>An error is shown when flitering from inventory page</td>
        <td>Chrome v120.0.6099</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials and password &quot;&quot;secret_sauce&quot;&quot;</td>
        <td>1. Click on filter option<br>2. Select &quot;&quot;Name (A to Z)&quot;&quot;</td>
        <td>Products are filtered from A to Z</td>
        <td>Error message &quot;Sorting is broken! This error has been reported to Backtrace&quot;</td>
        <td>Major</td>
        <td>Medium</td>
    </tr>
    <tr>
        <td>BG003</td>
        <td>Filter &quot;Price (High to low)&quot; doesn&#39;t work</td>
        <td>When filtering &quot;Price (High to low)&quot; items are filtered randomly</td>
        <td>Chrome v120.0.6099</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials and password &quot;&quot;secret_sauce&quot;&quot;</td>
        <td>1. Click on filter option<br>2. Select &quot;&quot;Price (High to low)&quot;&quot;</td>
        <td>Products are filtered from High to low price</td>
        <td>When filtering &quot;Price (High to low)&quot; items are filtered randomly</td>
        <td>Major</td>
        <td>High</td>
    </tr>
    <tr>
        <td>BG004</td>
        <td>Image for &quot;Sauce Labs Backpack&quot; doesn&#39;t correspond to the item</td>
        <td>Image for &quot;Sauce Labs Backpack&quot; shows a dog instead of a bag</td>
        <td>Chrome v120.0.6099</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials and password &quot;&quot;secret_sauce&quot;&quot;</td>
        <td>1. Check image on inventory page for &quot;Sauce Labs Backpack&quot;</td>
        <td>Image for &quot;Sauce Labs Backpack&quot; corresponds to the item</td>
        <td>Image for &quot;Sauce Labs Backpack&quot; shows a dog instead of a bag</td>
        <td>Major</td>
        <td>High</td>
    </tr>
    <tr>
        <td>BG005</td>
        <td>Price for &quot;Sauce Labs BIke Light&quot; doesn&#39;t match</td>
        <td>Price for &quot;Sauce Labs BIke Light&quot; doesn&#39;t match the one in inventory page vs the price inside the item itself </td>
        <td>Chrome v120.0.6099</td>
        <td>Access https://www.saucedemo.com/<br>User is logged in with &quot;&quot;error_user&quot;&quot; credentials and password &quot;&quot;secret_sauce&quot;&quot;</td>
        <td>1. Verify price in inventory page for &quot;&quot;Sauce labs bike light&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>2. Click on &quot;&quot;Sauce labs bike light&quot;&quot;</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>3. Confirm price matches&quot;</td>
        <td>Prices on inventory page for &quot;Sauce labs bike light&quot; vs the price in the item itself are the same ($9.99)</td>
        <td>Price for &quot;&quot;Sauce Labs BIke Light&quot;&quot; doesn&#39;t match the one in inventory page ($80.72) vs the price inside the item itself ($9.99)<br></td>
        <td>Major</td>
        <td>High</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>

## 📊 Jira Lifecycle Management
I managed the identified bugs through a standard Kanban workflow in Jira.

### Kanban Board View
<img width="1362" height="311" alt="jira-board" src="https://github.com/user-attachments/assets/c92f7a20-11c1-46cd-8511-b485b8f25d8c" />


### Sample Bug Report (Jira Detail)
<img width="877" height="762" alt="Bug-detail" src="https://github.com/user-attachments/assets/f10920d7-65e7-4117-be7f-d7cfda8512da" />


## 🎯 Key Findings
- Found **5 high-priority defects** affecting core business logic (Pricing, Cart Management, and Filtering).
- Identified visual regressions and data mapping errors using the 'error_user' credential.

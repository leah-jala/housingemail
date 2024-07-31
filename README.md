# Housing Emails Script - User Instructions

## Overview
This document provides detailed instructions on how to use the Housing Emails script to send housing assignment emails to students. The script includes functionalities to validate email addresses, send personalized emails to students, and handle errors gracefully.

## Setup Instructions

### 1. Prepare the Spreadsheet
1. **Existing Spreadsheet:** Continue using the current spreadsheet by saving results into a new tab (e.g., Fall 2024) or create a copy of the spreadsheet for new terms.
2. **Permissions:** Grant necessary permissions when using the existing spreadsheet or any new copies for the first time. This is required for any user accessing the services.
3. **Update Tabs:** Ensure the following tabs are updated:
   - Addresses
   - Rates
   - Single Room
   - Configuration
4. **Data Preparation:**
   - Insert data into columns A-I on the Data Prep Tab.
   - Do not move or add any columns as the script accesses columns based on their position.
   - Use provided formulas to populate columns D (if needed) and J-M on the Data Prep Tab and Formulas Tab. Click on the cell to activate the drop-down.
5. **Test Data:** Verify that the email text displays as expected using the provided data.

### 2. Test Your Data
1. **Testing Conditions:** Copy rows related to the conditions you wish to test to the Housing Assignment tab. Ensure to include roommates and use your own email for testing.
2. **Send Test Emails:** Navigate to the custom menu "Housing Emails" and select "Send Emails" to send the test emails.
3. **Transfer Data:** 
   - Clear the Housing Assignment tab of its data after testing.
   - Copy data from the Data Prep tab using `Ctrl+A` and paste it into the Housing Assignment tab using `Ctrl+Shift+V` to paste values only (excluding formulas).
4. **Modify Template:** To change the email template, go to `Extensions > App Script` in the menu and edit the `template.html` file. HTML instructions are provided below.
5. **Final Steps:** When finished, save the data into a new tab or a different spreadsheet.

## Using the Custom Menu
1. **Access the Custom Menu:** Open the Google Sheets document.
2. **Housing Emails Menu:** In the top menu, find the "Housing Emails" menu.
3. **Instructions:** Select "Instructions" to view detailed instructions.
4. **Send Emails:** Select "Send Emails" to execute the script and send housing assignment emails.

## HTML Instructions
### How to Use HTML Tags
- **Paragraph:** Use the `<p>` tag.
  ```html
  <p>This is a paragraph.</p>
  ```
- **Line Break:** Use the `<br>` tag.
  ```html
  A closing tag is not required.<br>
  ```
- **Link:** Use the `<a>` tag.
  ```html
  <a href="https://www.example.com">Visit Example</a>
  ```

## Error Handling
- **Missing Information:** If required information is missing for a student, the corresponding row will be highlighted in pink, and an error message will be added in the "Email Sent" column.
- **Email Send Failure:** If an email fails to send, the row will be highlighted in pink, and an error message will be recorded in the "Email Sent" column.
- **Invalid Emails:** If there are invalid email addresses, a pop-up alert will notify the user to correct them before re-running the script.

## Technical Details
### `onOpen` Function
This function adds a custom menu ("Housing Emails") to the Google Sheets UI when the document is opened.

### `showInstructions` Function
This function displays instructions in a modal dialog.

### `sendHousingAssignmentEmails` Function
This function:
1. Validates email addresses.
2. Retrieves housing assignment data from the "HousingAssignment" sheet.
3. Sends personalized emails to students.
4. Handles errors by highlighting problematic rows and logging error messages.

### `sendEmail` Function
This function sends an email to a student using data provided by the `sendHousingAssignmentEmails` function.

### `validateEmails` Function
This function validates email addresses and highlights invalid ones in red.

## Closing the Instructions Modal
Click the "Close" button in the instructions modal to close it.

---

By following these instructions, you can efficiently use the Housing Emails script to manage and send housing assignment emails to students. For any issues or further customization, refer to the provided HTML instructions and modify the script as needed.

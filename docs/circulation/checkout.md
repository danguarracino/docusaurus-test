---
sidebar_position: 1
---

# Circulating Items

## Check Out

### Regular Items

1) To check out an item click **Check Out Items** from the Circulation and Patrons toolbar, or select **Circulation** -> **Check Out**.

![Check Out Items menu in the Circulation and Patrons toolbar.](img/checkout_menu_web_client.png)

2) Scan or enter patron’s barcode and click **Submit** if entering barcode manually. If scanning, number is submitted automatically.

![Patron barcode entry screen with a submit button.](img/retrieve_patron_web_client.png)

3) Scan or enter item barcode manually, clicking **Submit** if manual.

image::img/checkout_item_barcode_web_client.png[Item barcode entry screen with a submit button.] 

4) Due date is now displayed.

![Display showing the due date for a checked-out item.](img/due_date_display_web_client.png)

5) When all items are scanned, click the **Done** button to generate slip receipt or to exit patron record if not printing slip receipts. 

### Pre-cataloged Items

1) Go to patron’s **Check Out** screen by clicking **Circulation** -> **Check Out Items**.

2) Scan the item barcode.

3) At prompt, enter the required information click **Precat Checkout**. 

![Pre-cataloged item checkout screen with fields for item information.](img/precat_web_client.png)

On check-in, Evergreen will prompt staff to re-route the item to cataloging.

This screen does not respond to the enter key or carriage return provided by a barcode scanner when the cursor is in the ISBN field.  This behavior prevents pre-cataloged items from being checked out before you are done entering all the desired information.

This requires the _CREATE_PRECAT_ permission.  All form elements in the
dialog other than the Cancel button will be disabled if the current user
lacks the CREATE_PRECAT permission.

### Due Dates

Circulation periods are pre-set. When items are checked out, due dates are automatically calculated and inserted into circulation records if the **Specific Due Date** checkbox is not selected on the Check Out screen. The **Specific Due Date** checkbox allows you to set a different due date to override the pre-set loan period.

Before you scan the item, select the **Specific Due Date** checkbox. Enter the date in yyyy-mm-dd format. This date applies to all items until you change the date, de-select the **Specific Due Date** checkbox, or quit the patron record.

![Specific Due Date checkbox with date entry field.](img/specify_due_date1_web_client.png)

### Strict Barcode

The 'Strict Barcode' checkbox can appear next to barcode inputs on the checkout, checkin, renewal, and offline circulation pages.

If checked, it will examine the barcode value to see if it contains only digits and meets the "Mod10" checkdigit algorithm. This checkdigit algorithm is often used by library barcodes that use the "Codabar" symbology.

If the barcode does not meet the conditions, a "bad barcode" alert will be displayed. Staff are given the option to accept and continue using the barcode as input.
"Strict Barcode" is only useful for libraries whose barcodes use the Mod10 checkdigit algorithm. However, several other checkdigit algorithms and symbologies are in use by libraries.

![Example of Strict Barcode Checkbox](img/strict_barcode.png)

### Email Checkout Receipts

This feature allows patrons to receive checkout receipts through email at the circulation desk and in the Evergreen self-checkout interface.  Patrons need to opt in to receive email receipts by default and must have an email address associated with their account.  Opt in can be staff mediated at the time of account creation or in existing accounts.  Patrons can also opt in directly in their OPAC account or through patron self-registration.  This feature does not affect the behavior of checkouts from SIP2 devices.

#### Staff Client Check Out

When a patron has opted to receive email checkout receipts by default, an envelope icon representing email will appear next to the receipt options in the Check Out screen.  A printer icon representing a physical receipt appears if the patron has not opted in to the default email receipts.

![Envelope icon indicating the option to email checkout receipts.](img/ereceipts5_web_client.PNG)

Staff can click **Quick Receipt** and the default checkout receipt option will be triggered—an email will be sent or the receipt will print out.  The Quick Receipt option allows staff to stay in the patron account after completing the transaction.  Alternatively, staff can click **Done** to trigger the default checkout receipt and close out the patron account.  By clicking on the arrow next to the Quick Receipt or Done buttons, staff can select which receipt option to use, regardless of the selected default.  The email receipt option will be disabled if the patron account does not have an email address.

#### Self Checkout

In the Self Checkout interface, patrons will have the option to select a print or email checkout receipt, or no receipt.  The radio button for the patron’s default receipt option will be selected automatically in the interface.  Patrons can select a different receipt option if desired.  The email receipt radio button will be disabled if there is no email address associated with the patron’s account.

![Self Checkout interface with options for print or email receipts.](img/ereceipts6_web_client.PNG)

#### Opt In

**Staff Mediated Opt In At Registration**

Patrons can be opted in to receive email checkout receipts by default by library staff upon the creation of their library account.  Within the patron registration form, there is a new option below the Email Address field to select _Email checkout receipts by default?_.  Select this option if the patron wants email checkout receipts to be their default.  Save any changes.

![Email checkout receipts opt-in option in the patron registration form.](img/ereceipts1_web_client.PNG)

**Staff Mediated Opt In After Registration**

Staff can also select email checkout receipts as the default option in a patron account after initial registration.  Within the patron account go to **Edit** and select _Email checkout receipts by default?_.  Make sure the patron also has an email address associated with their account.  Save any changes.

![Email checkout receipts default option in the patron account edit screen.](img/ereceipts2_web_client.PNG)

**Patron Opt In – Self-Registration Form**

If your library offers patrons the ability to request a library card through the patron self-registration form, they can select email checkout receipts by default in the initial self-registration form:

![Self-registration form with the option to select email checkout receipts by default.](img/ereceipts3_web_client.PNG)

**Patron Opt In - OPAC Account**

Patrons can also opt in to receive email checkout receipts by default directly in their OPAC account.  After logging in, patrons can go to **Account Preferences->Notification Preferences** and enable _Email checkout receipts by default?_ and click **Save**.

![Notification Preferences section in the OPAC account with the option to enable email checkout receipts.](img/ereceipts4_web_client.PNG)

#### Email Checkout Receipt Configuration

Email checkout receipts will be sent out through a Notifications/Action Trigger called Email Checkout Receipt.  The email template and action trigger can be customized by going to **Administration->Local Administration->Notifications/Action Trigger->Email Checkout Receipt**.

## Check In ==

### Regular check in ===

1) To check in an item click **Check In Items** from the Circulation and Patrons toolbar, or select **Circulation** -> **Check In**.

![Check In Items menu in the Circulation and Patrons toolbar.](img/check_in_menu_web_client.png)

2) Scan item barcode or enter manually and click **Submit**.

![Item barcode entry screen with a submit button.](img/checkin_barcode_web_client.png)

3) If there is an overdue fine associated with the checkin, an alert will appear at the top of the screen with a fine tally for the current checkin session. To immediately handle fine payment, click the alert to jump to the patron’s bill record.

![Overdue check-in alert with a fine tally.](img/overdue_checkin_web_client.png)

4) If the checkin is an item that can fill a hold, a pop-up box will appear with patron contact information or routing information for the hold.

5) Print out the hold or transit slip and place the item on the hold shelf or route it to the proper library.

6) If the item is not in a state acceptable for hold/transit (for instance, it is damaged), select the line of the item, and choose **Actions** -> **Cancel Transit**.  The item will then have a status of _Canceled Transit_ rather than _In Transit_.

![Actions Menu - Cancel Transit](img/Check_In-Cancel_Transit.png)

### Backdated check in

This is useful for clearing a book drop.

1) To change effective check-in date, select **Circulation** -> **Check In Items**. In **Effective Date** field enter the date in yyyy-mm-dd format.

![Effective Date field for backdated check-ins.](img/backdate_checkin_web_client.png)

2) The new effective date is now displayed in the red bar above the Barcode field.

![Effective date displayed in red bar above the barcode field.](img/backdate_red_web_client.png)

3) Move the cursor to the **Barcode** field. Scan the items. When finishing backdated check-in, change the **Effective Date** back to today’s date.

### Backdate Post-Checkin

After an item has been checked in, you may use the Backdate Post-Checkin function to backdate the check-in date.

1) Select the item on the Check In screen, click **Actions** -> **Backdate Post-Checkin**.

![Backdate Post-Checkin action in the Actions menu.](img/backdate_post_checkin_web_client.png)

2) In **Effective Date** field enter the date in yyyy-mm-dd format.  The check-in date will be adjusted according to the new effective check-in date.

![Effective Date field for backdating post-checkin.](img/backdate_post_date_web_client.png)

<a name="checkin_modifiers"></a>**Checkin Modifiers**

===================================================
At the right bottom corner there is a **Checkin Modifiers** pop-up list. The options are:

* **Ignore Pre-cat Items**: No prompt when checking in a pre-cat item. Item will be routed to Cataloguing with Cataloguing status.
* **Suppress Holds and Transit**: Item will not be used to fill holds or sent in transit. Item has Reshelving status.
* **Amnesty Mode/Forgive Fines**: Overdue fines will be voided if already created or not be inserted if not yet created (e.g. hourly loans).
* **Auto-Print Hold and Transit Slips**: Slips will be automatically printed without prompt for confirmation.
* **Clear Holds Shelf**: Checking in hold-shelf-expired items will clear the items from the hold shelf (holds to be cancelled).
* **Retarget Local Holds**: When checking in in process items that are owned by the library, attempt to find a local hold to retarget. This is intended to help with proper targeting of newly-catalogued items.
* **Retarget All Statuses**: Similar to Retarget Local Holds, this modifier will attempt to find a local hold to retarget, regardless of the status of the item being checked in. This modifier must be used in conjunction with the Retarget Local Holds modifier.
* **Capture Local Holds as Transits**: With this checkin modifier, any local holds will be given an in transit status instead of on holds shelf. The intent is to stop the system from sending holds notifications before the item is ready to be placed on the holds shelf and item will have a status of in-transit until checked in again. If you wish to simply delay notification and allow time for staff to process item to holds shelf, you may wish to use the Hold Shelf Status Delay setting in Library Settings Editor instead. See Local Administration section for more information.
* **Manual Floating Active**: Floating Groups must be configured for this modifier to function. The manual flag in Floating Groups dictates whether or not the "Manual Floating Active" checkin modifier needs to be active for a copy to float. This allows for greater control over when items float. 
* **Update Inventory**: When this checkin modifier is selected, scanned barcodes will have the current date/time added as the inventory date while the item is checked in. 

These options may be selected simultaneously. The selected option is displayed in the header area.

![Web client check-in modifiers](img/checkinmodifiers-with-inventory2.png)
===================================================
  
== Renewal and Editing the Item’s Due Date ==

Checked-out items can be renewed if your library’s policy allows it. The new due date is calculated from the renewal date. Existing loans can also be extended to a specific date by editing the due date or renewing with a specific due date.

### Renewing via a Patron's Account

1) Retrieve the patron record and go to the **Items Out** screen.

![Items Out screen in the patron record.](img/items_out_click_web_client.png)

2) Select the item you want to renew. Click on **Actions** -> **Renew**. If you want to renew all items in the account, click **Renew All** instead.

![Renew action in the Items Out screen.](img/renew_action_web_client.png)

3) If you want to specify the due date, click **Renew with Specific Due Date**.

![Renew items with a specific due date action in Items Out screen.](img/renew_specific_date_web_client.png)

You will be prompted to select a due date. Once done, click **Submit**.

![Renew items with a specific due date](img/renew_specific_date_submit.png)

### Renewing by Item Barcode
1) To renew items by barcode, select **Circulation** -> **Renew Items**.

2) Scan or manually entire the item barcode.

![Renew Items screen with item barcode entry.](img/renew_item_web_client.png)

3) If you want to specify the due date, click **Specific Due Date** and enter a new due date in yyyy-mm-dd format.

![Specific Due Date entry field for renewing items.](img/renew_item_calendar_web_client.png)

### Editing Due Date

1) Retrieve the patron record and go to the **Items Out** screen.

2) Select the item you want to renew. Click on **Actions** -> **Edit Due Date**.

![Edit Due Date action in the Items Out screen.](img/edit_due_date_action_web_client.png)

3) Enter a new due date in yyyy-mm-dd format in the pop-up window, then click **OK**.

Editing a due date is not included in the renewal count.

### Overriding Errors in Items Out 

As of 3.8, there is new work which streamlines handling of overridable events encountered in the Patron Items Out interface of the staff client. The main user-visible part of this work is a new Action Override modal which is presented to the staff user when an overridable action is encountered.

The primary target of the work is for actions from the Items Out part of the Patron interface, but due to code sharing the Checkout interface benefits as well.

There are two kinds of overrides addressed in this work, both in the Patron interface:

* ***Action Override*** - this is when a staff user attempts to make an action (i.e. Renew) succeed after the system had alerted the user to exceptions (i.e. Patron Max Fines).  
* ***Permission Override*** - this is when a staff user attempts an action but encounters a permission-denied alert, and thus needs temporary credentials (i.e. a supervisor’s login) to re-attempt the action.

In the case of both overrides, this work attempts to minimize the number of times a staff user has to click through an error. Specifically, if a staff member overrides an exception, they will in most cases be able to instruct Evergreen to “remember” this override for as long as the staff member is working on a specific patron record. 

Similarly, if a supervisor enters a permissions override for a specific permission-denied alert, Evergreen will “remember” this override for as long as the staff member is working on a specific patron record. 

Both action overrides and permission overrides will be “forgotten” once the patron record is closed and/or the staff user navigates away from that patron record.

The Override modal has been changed to include new actions as well as a new checkbox for “Automatically override for subsequent items?” 

There are three possible actions in the new Override modal:

* ***Force Action*** - this will attempt to override the exception(s). If the box next to “Automatically override for subsequent items?” is checked, Evergreen will remember this and auto-override those specific exception(s) for the rest of the time the staff user is working in this patron record. 
* ***Skip*** - this button tells Evergreen to ignore the current item (i.e., skip the renewal action), but if the box next to “Automatically override for subsequent items?” is checked, Evergreen will still remember future overrides on this exception.
* ***Cancel*** - this will close the modal and abort the action. It will not roll back any actions (i.e., if two items are renewed and the modal shows on the third item, clicking cancel will not roll back the renewals that have already completed).

An example of the new Override modal is shown below. In this example, the `PATRON_EXCEEDS_FINES` exception has been set to automatically override for subsequent items. This means that the next time Evergreen encounters this exception in this specific patron session, Evergreen will automatically attempt to override it. The `MAX_RENEWALS_REACHED` exception has NOT been set to automatically override for subsequent items. This means that the next time Evergreen encounters this exception in this specific patron session, it will ask again about an override.

![New Override Modal](img/new_override_modal.png)

In stock Evergreen, the following states will present an exception (i.e. ask for an override) on checkout and/or renew:

* Shelving Locations with _Can Circulate?_ set to false
* Item Statuses of Bindery, Claimed Returned, Long Overdue, Lost, Lost and Paid, Missing, On Holds Shelf [for another patron]
* Item-level data: Certain statuses (above), certain shelving locations (above), deposit = true, reference = true

Certain events are not able to be batch-overridden, such as when an item with an existing open circulation is presented at checkout. Other events are not able to be overridden at all, including `ACTOR_USER_NOT_FOUND` and `ASSET_COPY_NOT_FOUND`.

Stock penalty codes (`STAFF_C`, `STAFF_CH`, `STAFF_CHR`, `STAFF_H`, `STAFF_HR`, `STAFF_R`) that can be encountered as events are auto-overrideable by default, and may present an Action Override modal.

## Mark Items ==

Items can have their status changed via the _Mark_ functions on the Actions menus. 

### Claims Never Checked Out

If a patron believes an item was erroneously checked out on their account and staff cannot locate it 
to check it in the item can be marked as claims never checked out.

1. Go to the _Items Out_ tab in the patron account.
2. Select the item and click **Actions -> Mark Claims Never Checked Out**.

   ![Mark Claims Never Checked Out action in the Items Out screen.](img/mark-claims-never-checked-out-1.png)

3. A pop-up appears where staff can confirm that they wish to mark the item by clicking **OK/Continue**.
4. The item is checked in and set to _Missing_. The item is no longer associated with the patron’s account.

:::note

Libraries may wish to routinely run reports on items with the status of _Missing_ so they can be searched for
:::

### Claims Returned

If a patron believes an item out on their account was returned and staff cannot locate it to check it in
the item can be marked as claims returned. 

1. Go to the _Items Out_ tab in the patron account.
2. Select the item and click **Actions -> Mark Claims Returned**.

   ![Mark Claims Returned action in the Items Out screen.](img/mark-claims-returned-1.png)

3. Enter the date on which the patron claims they returned the item and click **Submit**.  If the chosen date is 
in the past any overdue fines will be adjusted accordingly.

   ![Field for entering the date the item was claimed returned.](img/mark-claims-returned-2.png)

4. The item’s status is updated to _Claimed Returned_. It remains associated with the patron’s account and 
is now displayed on the _Other/Special Circulations_ tab. The value in the **Claims-returned Count** field 
in the patron record is automatically increased.

   ======
   Some libraries prefer to use the status _Missing_.  This can be set using the library setting 
   _Claim Return: Mark copy as missing_.
   ====== 

   ![View of a claims returned item in a patron's Other/Special Circulations tab.](img/mark-claims-returned-3.png)

5. The patron’s **Claims-returned Count** is automatically increased. This can be viewed in the patron summary
and the _Edit_ tab.

   ======
   Libraries can use the library setting _Max Patron Claims Returned Count_ to set a maximum number of items
   a patron can claim as returned before a staff override is required.
   ====== 

A claimed returned items is resolved when it is checked in or when the status is updated to _Missing_ or _Lost_
following local library policy.  An alert displays on check in to let staff know a claimed returned
item has been found. If there is an outstanding bill associated with it, the item will not disappear 
from the **Items Out** screen. It will disappear when the outstanding bills are resolved. When an 
item is located staff may wish to adjust the patron’s **Claims-returned Count** accordingly on the _Edit_ tab.

### Damaged

If a patron damages an item it can be marked as damaged at check in, via the Item Status interface, or
from within a patron’s account.

1. On the appropriate interface select the item and click **Actions -> Mark Damaged**

   ![Mark Damaged action in the Item Status interface.](img/mark-damaged-1.png)

2. A pop-up appears indicating that the item will be marked damaged.  Click **Submit**.
3. If your library has the library setting _Charge item price when marked damaged_ set to True a second
pop-up will appear.
   1. If needed, adjust the amount being billed.  The processing fee from the library setting 
   _Charge processing fee for damaged items_ is included in the total. 
   2. Select the bill type from the drop down menu.
   3. If needed, add a note.
   4. If you are not charging the patron in this particular case, click **No Charge**.
   5. Click **Submit**.

      !["Damaged item billing dialog with fields for adjusting the amount](img/mark-damaged-2.png)

4. The item’s status is updated to _Damaged_ and removed from the patron’s account. If the patron has 
been billed for the damage the bill will display in the _Bills_ tab.  The bill displays as a single charge
which includes the processing fee. 

A damaged item is resolved when it is checked in to return it to circulation, when the status is updated to 
_Discard/Weed_, or when the item is deleted.  An alert displays on check in to let staff know a damaged
item has been checked in.

======
Checking in a damaged item does not affect any bills that were generated when the item was set to _Damaged_.
======

### Discard/Weed

If an item is slated to be removed from the collection it can be marked as discard/weed at check in
or via the Item Status interface.  Libraries may wish to use the _Discard/Weed_ status when items to be
discarded need to be reviewed before being deleted.

1. On the appropriate interface select the item and click **Actions -> Mark as Discard/Weed**.

   ![Mark as Discard/Weed action in the Item Status interface.](img/mark-discard-1.png)

2. A pop-up appears where staff can confirm that they wish to mark the item by clicking **OK/Continue**.
3. The item is set to _Discard/Weed_.

A discarded item is resolved when it is checked in to return it to circulation or deleted from Evergreen.

======
Staff may wish to put discarded items into item buckets to make it easier for subsequent staff to view
and work with the items. 
======

### Missing

If an item cannot be located it can be marked as missing via the Item Status interface or from within a 
patron’s account.

1. On the appropriate interface select the item and click **Actions -> Mark Missing**

   ![Mark Missing action in the Item Status interface.](img/mark-missing-1.png)

2. A pop-up appears where staff can confirm that they wish to mark the item by clicking **OK/Continue**.
3. If the item is currently checked out a second pop-up will ask staff to confirm that they wish to check
in the item.
4. The item is set to _Missing_ and, if previously checked out, is no longer associated with the patron’s
account.

A missing item is resolved when it is found and checked in or when it is deleted from Evergreen.

### Missing Pieces

If an item is returned with pieces missing it can be marked as missing pieces from Check In or
the Scan Item as Missing Pieces interface. The feature currently functions slightly different depending
on which interface it is accessed through.

#### Mark Missing Pieces via Check In

1. Go to **Circulation -> Check In**.
2. Check the item in.
3. Select the item and click **Actions -> Mark Missing Pieces**.

   ![Mark Missing Pieces action in the Check In interface.](img/mark-missing-pieces-1.png)

4. A pop-up appears where staff can confirm that they wish to mark the item by clicking **OK/Continue**.

5. A print dialog will appear.  Staff can print the slip to keep with the item.
6. The _Create Note_ pop-up will appear.  Use the pop-up to create a note, 
alert, or block on the patron’s account.  This note can be set as patron visible so it displays to the 
patron in My Account.
7. Click **OK**.
8. The note is applied to the last borrower’s account and the item is set to _Damaged_ and checked back out
to the patron’s account.

   ======
   This method of setting an item as missing pieces is missing the letter that is generated at the end of the 
   process.  If that letter is important to your workflow you should always mark items missing pieces
   via the Scan Item as Missing Pieces interface.
   ======

#### Scan Item as Missing Pieces

1. Go to **Circulation -> Scan Item as Missing Pieces**.
2. Scan the item’s barcode.
3. Click **Mark Item as Missing Pieces?**.

   ![Mark Item as Missing Pieces button in the Scan Item as Missing Pieces interface.](img/mark-missing-pieces-2.png)

4. A print dialog will appear.  Staff can print the slip to keep with the item.
5. The _Create Note_ pop-up will appear.  Use the pop-up to create a note, 
alert, or block on the patron’s account.  

   ======
   This pop-up is the old Notes pop-up and is missing the functionality that allows staff to select the display
   depth and set a note as patron visible so it displays to the patron in My Account.
   ======

6. Click **OK**.

   ![Create Note pop-up for marking an item as Missing Pieces.](img/mark-missing-pieces-3.png)

7. The note is applied to the last borrower’s account and the item is set to _Damaged_ and renewed on the
patron’s account, if there are remaining renewals.
8. A letter is generated that can be edited and then printed and mailed to the patron.

A missing pieces item is resolved when the pieces are returned and the item is checked in or the pieces 
are never returned and the item is deleted.  Notes related to the item must be manually removed from
the patron’s account.

======
Libraries can choose to use a different item status for missing pieces instead of _Damaged_.  The 
library setting _Item Status for Missing Pieces_ is used to set this.
======

### Lost Items
1) To mark items Lost, retrieve patron record and click **Items Out**.

2) Select the item. Click on **Actions** -> **Mark Lost (by Patron)**.

![Mark Lost (by Patron) action in the Items Out screen.](img/mark_lost_web_client.png)

3) The lost item now displays as lost in the **Items Checked Out** section of the patron record.

![Lost item displayed in the Items Checked Out section of the patron record.](img/lost_section_web_client.png)

4) The lost item also adds to the count of **Lost** items in the patron summary on the left (or top) of the screen. 

![Lost items displayed in the patron summary.](img/patron_summary_checkouts_web_client.png)

Lost Item Billing
========================
- Marking an item Lost will automatically bill the patron the replacement cost of the item as recorded in the price field in the item record, and a processing fee as determined by your local policy. If the lost item has overdue charges, the overdue charges may be voided or retained based on local policy.
- A lost-then-returned item will disappear from the Items Out screen only when all bills linked to this particular circulation have been resolved. Bills may include replacement charges, processing fees, and manual charges added to the existing bills. 
- The replacement fee and processing fee for lost-then-returned items may be voided if set by local policy. Overdue fines may be reinstated on lost-then-returned items if set by local policy.
========================

### Refunds for Lost Items

If an item is returned after a lost bill has been paid and the library’s policy is to void the replacement fee for lost-then-returned items, there will be a negative balance in the bill. A refund needs to be made to close the bill and the circulation record. Once the outstanding amount has been refunded, the bill and circulation record will be closed and the item will disappear from the Items Out screen.

If you need to balance a bill with a negative amount, you need to add two dummy bills to the existing bills. The first one can be of any amount (e.g. $0.01), while the second should be of the absolute value of the negative amount. Then you need to void the first dummy bill. The reason for using a dummy bill is that Evergreen will check and close the circulation record only when payment is applied or bills are voided.

## In-house Use (F6) ==
1) To record in-house use, select **Circulation** -> **Record-In House Use**, click **Check Out** -> **Record In-House Use** on the circulation toolbar , or press **F6**. 
 
image::circulating_items_web_client/record_in_house_action_web_client.png[Record In-House Use option in the Circulation toolbar.]
 
2) To record in-house use for cataloged items, enter number of uses, scan 
 barcode or type barcode and click **Submit**.
 
image::circulating_items_web_client/in_house_use_web_client.png[In-House Use entry screen for cataloged items.]
 
====================================
There are two independent library settings that will allow copy alerts to display when scanned in In-house Use:
**Display copy alert for in-house-use** set to true will cause an alert message to appear, if it has one, when recording in-house-use for the copy.
**Display copy location check in alert for in-house-use** set to true will cause an alert message indicating that the item needs to be routed to its location if the location has check in alert set to true.
====================================
 
3) To record in-house use for non-cataloged items, enter number of uses, choose non-cataloged type from drop-down menu, and click **Submit**.

![In-House Use entry screen for non-cataloged items.](img/in_house_use_non_cat.png)

[NOTE] 
The statistics of in-house use are separated from circulation statistics. The in-house use count of cataloged items is not included in the items' total use count.

## How Item Statuses Work ==

This section goes over all item statuses and their relationship to the system.

### List of Item Statuses

-**Available**: Item is available for checkout.

-**Checked out**: Item is checked out to a patron account.  This status does not indicate whether or not the item is overdue.

-**Claims Returned**: item has been claimed as returned by the patron. This option as an item status is controlled by a library setting.

-**Bindery**: Manually set for items that are being sent out to be re-bound.

-**Lost**: Item has been checked out past a due date threshold or is no longer in a patron’s possession while they’re still responsible for the item. Can be automated based on due date, or manually set by staff.

-**Missing**: Item cannot be found on the shelves - either manually set, or applied upon “claims returned” (as well as claims never checked out?)

-**In process**: An item is newly cataloged and waiting to be checked in.

-**In transit**: Item has been checked in and is being sent to a different library, whether as a return to its home library, or to fulfill a hold.

-**Reshelving**: A transitional status for items that have been checked in, and need reshelving.

-**On holds shelf**: Item is captured for a hold of a patron at their pickup location and waiting to be checked out.

-**On order**: A title has been ordered, but the physical copy has not yet been processed and added to the catalog. Can allow patrons to discover forthcoming acquisitions, and to place holds prior to the library receiving the item in question.

-**ILL**: Inter-library loan.

-**Cataloging**: An item has been pulled to be edited by a cataloger.

-**Reserves**: In reserves collection.

-**Discard/Weed**: Item has been manually flagged for removal from the collection, but has not yet been deleted.

-**Damaged**: Item is damaged and the patron was billed.

-**On reservation shelf**: Used with room/booking module. When an item has been booked/reserved, it is placed in a unique location, ready for pick-up.

-**Long Overdue**: Item has been checked out past a due date threshold.

-**Lost and Paid**: Item was marked lost and the patron paid the replacement cost.

-**Canceled Transit**: Item that was in transit status but was then canceled.

### Actions that Change Item Statuses

-**Available**: checking in an item that isn’t eligible for a hold

-**Claims Returned**: item is marked as claimed returned via the patron account

-**In Transit**: item is captured for a transit to another location at check in

-**On reservation shelf**: Item is captured for reservation through the Booking module.

-**On order**: Items is created via activating a purchase order in Acquisitions.

-**In process**: An item is newly cataloged and waiting to be checked in. Also, item is received in acquisitions.

-**Damaged**: Marked Damaged needs to be executed on a screen 

## Item Status Properties ==

| Name | Holdable? | OPAC Visible? | Sets copy active? | Is available? | Assignable? |
| --- | --- | --- | --- | --- | --- |
| Available | Yes | Yes | Yes | Yes | System controller |
| Bindery | No | No | No | No | Yes |
| Canceled Transit | Yes | Yes | No | No | System controlled |
| Cataloging | No | No | No | No | Yes |
| Checked out | Yes | Yes | Yes | No | System controlled |
| Damaged | No | No | No | No | Yes |
| Discard/weed | No | No | No | No | Yes |
| ILL | No | No | Yes | No | Yes |
| In process | Yes | Yes | No | No | Yes |
| In receiving | Yes | Yes | No | No | System controlled |
| In transit | Yes | Yes | No | No | System controlled |
| Long Overdue | No | No | No | No | System controlled |
| Long Overdue (Legacy) | No | No | No | No | Yes |
| Lost | No | No | No | No | Yes |
| Lost and paid | No | No | No | No | Yes |
| Missing | No | No | No | No | Yes |
| On holds shelf | Yes | Yes | Yes | No | System controlled |
| On order | No | No | No | No | Yes |
| On reservation shelf | No | No | Yes | No | Yes |
| Reserves | No | No | Yes | No | Yes |
| Reshelving | Yes | Yes | Yes | Yes | System controlled |
| Temporarily unavailable | No | No | No | No | Yes |

The following properties can be set for each status:

-**Holdable** - If checked, users can place holds on copies in this status, provided nothing else prevents holds. If unchecked, users cannot place holds on copies in this status.

-**OPAC Visible** - If checked, copies in this status will be visible in the public catalog. If unchecked, copies in this status will Not be visible in the public catalog, but they will be visible when using the catalog in the staff client.
Sets copy active - If checked, moving a copy that does not yet have an active date to this status will set the active date. If the copy already has an active date, then no changes will be made to the active date. If “No”, this status will never set the copy’s active date.

-**Is Available** - If checked, copies with this status will appear in catalog searches where “limit to available” is selected as a search filter. Also, copies with this status will check out without status warnings. By default, the “Available” and “Reshelving” statuses have the “Is Available” flag set as true/yes.

-**Hopeless Holds** (as of ver. 3.6): _need info_

Default Evergreen statuses have a further property:

-**Assignable** – Status is system controlled and editing to either assign or change in the Holdings editor is not always possible.

## Item Status ==

The Item Status screen is very useful. Many actions can be taken by either circulation staff or catalogers on this screen. Here we will cover some circulation-related functions, namely checking item status, viewing past circulations, inserting item alert messages, marking items missing or damaged, etc.

### Checking item status

1) To check the status of an item, select **Search** -> **Search for copies by Barcode**.

![Search for copies by Barcode option in the Search menu.](img/item_status_menu_web_client.png)

2) Scan the barcode or type it and click **Submit**. The current status of the item is displayed with selected other fields. You can use the column picker to select more fields to view.

![Item status display with selected fields after barcode submission.](img/item_status_barcode_web_client.png)

3) Click the **Detail View** button and the item summary and circulation history will be displayed.

![Detail View button showing item summary and circulation history.](img/item_status_altview_web_client.png)

4) Click **List View** to go back.

![List view in Item Status.](img/item_status_list_view_web_client.png)

If the item’s status is "Available", the displayed due date refers to the previous circulation’s due date.

Upload From File allows you to load multiple items saved in a file on your local computer. The file contains a list of the barcodes in text format. To ensure smooth uploading and further processing on the items, it is recommended that the list contains no more than 100 items.

### Viewing past circulations
1) To view past circulations, retrieve the item on the **Item Status** screen as described above.

2) Select **Detail view**.

![Recent Circ History option in the Detail view.](img/last_few_circs_action_web_client.png)

3) Choose **Recent Circ History**.  The item’s recent circulation history is displayed.

![Recent circulation history display for an item.](img/last_few_circs_display_web_client.png)

4) To retrieve the patron(s) of the last circulations, click on the name of the patron.  The patron record will be displayed.

The number of items that displays in the circulation history can be set in Local **Administration** -> **Library Settings Editor**.

You can also retrieve the past circulations on the patron’s Items Out screen and from the Check In screen.

### Marking items damaged or missing and other functions
1) To mark items damaged or missing, retrieve the item on the **Item Status** screen.

2) Select the item. Click on **Actions** -> **Mark Item Damaged** or **Mark Item Missing**.

![Mark items as missing or damaged from actions menu in Item Status screen.](img/mark_missing_damaged_web_client.png)

Depending on the library’s policy, when marking an item damaged, bills (cost and/or processing fee) may be inserted into the last borrower’s account. 

3) Following the above procedure, you can check in and renew items by using the **Check in Items** and **Renew Items** on the dropdown menu.

### Item alerts

The **Edit Item** function on the **Actions** dropdown list allows you to edit item records. Here, we will show you how to insert item alert messages by this function. See cataloging instructions for more information on item editing.

1) Retrieve record on **Item Status** screen.

2) Once item is displayed, highlight it and select **Actions** -> **Edit** -> **Item**.

3) The item record is displayed in the **Holdings Editor**.

4) Click the **Item Alerts** button in the **Add Item Alerts** box under the **Miscellaneous** column.

![Item Alerts button in the Holdings Editor.](img/holdings_editor_add_item_alert.png)

5) A window appears, where you can select the alert type, i.e., when the alert should appear for staff. Select the **Temporary** checkbox if you would like the alert to be removed after that specific action for the item is complete. Type in the message then click **Apply Changes**. 

![Managing item alerts window with examples of alert types shown in dropdown.](img/item_alert_window.png)

6) Back in the Holdings Editor, click **Apply All & Save** or **Apply, Save & Exit**.

![Item Alerts button in the Holdings Editor.](img/holdings_editor_save_options.png)

## Long Overdue Items ==

**Items Marked Long Overdue**

Once an item has been overdue for a configurable amount of time, Evergreen will mark the item long overdue in the borrowing patron’s account.  This will be done automatically through a Notification/Action Trigger.   When the item is marked long overdue, several actions will take place:

1. The item will go into the status of “Long Overdue” 
2. The accrual of overdue fines will be stopped

Optionally the patron can be billed for the item price, a long overdue
processing fee, and any overdue fines can be voided from the account.  Patrons
can also be sent a notification that the item was marked long overdue. And
long-overdue items can be included on the "Items Checked Out" or "Other/Special
Circulations" tabs of the "Items Out" view of a patron’s record. These are all
controlled by [library settings](#longoverdue_library_settings).
 
image::circulating_items_web_client/long_overdue1.png[Patron Account-Long Overdue]

**Checking in a Long Overdue item**

If an item that has been marked long overdue is checked in, an alert will appear on the screen informing the staff member that the item was long overdue.  Once checked in, the item will go into the status of “In process”.  Optionally, the item price and long overdue processing fee can be voided and overdue fines can be reinstated on the patron’s account.  If the item is checked in at a library other than its home library, a library setting controls whether the item can immediately fill a hold or circulate, or if it needs to be sent to its home library for processing.
 
image::circulating_items_web_client/long_overdue2.png[Long Overdue Checkin]
 
**Notification/Action Triggers**

Evergreen has two sample Notification/Action Triggers that are related to marking items long overdue.  The sample triggers are configured for 6 months.  These triggers can be configured for any amount of time according to library policy and will need to be activated for use.

* Sample Triggers
  * 6 Month Auto Mark Long-Overdue—will mark an item long overdue after the configured period of time
  * 6 Month Long Overdue Notice—will send patron notification that an item has been marked long overdue on their account

<a name="longoverdue_library_settings"></a>**Library Settings** 

The following Library Settings enable you to set preferences related to long overdue items:

* **Circulation: Long-Overdue Check-In Interval Uses Last Activity Date** —Use the
  long-overdue last-activity date instead of the due_date to determine whether
  the item has been checked out too long to perform long-overdue check-in
  processing. If set, the system will first check the last payment time,
  followed by the last billing time, followed by the due date. See also the
  "Long-Overdue Max Return Interval" setting.
* **Circulation: Long-Overdue Items Usable on Checkin** —Long-overdue items are usable on checkin instead of going "home" first
* **Circulation: Long-Overdue Max Return Interval** —Long-overdue check-in processing (voiding fees, re-instating overdues, etc.) will not take place for items that have been overdue for (or have last activity older than) this amount of time 
* **Circulation: Restore Overdues on Long-Overdue Item Return**
* **Circulation: Void Long-Overdue item Billing When Returned**
* **Circulation: Void Processing Fee on Long-Overdue Item Return**
* **Finances: Leave transaction open when long overdue balance equals zero** —Leave transaction open when long-overdue balance equals zero. This leaves the lost copy on the patron record when it is paid
* **Finances: Long-Overdue Materials Processing Fee**
* **Finances: Void Overdue Fines When Items are Marked Long-Overdue**
* **GUI: Items Out Long-Overdue display setting**

Learn more about these settings in the chapter about the
Library Settings Editor.

**Permissions to use this Feature**

The following permissions are related to this feature:

* COPY_STATUS_LONG_OVERDUE.override
  * Allows the user to check-in long-overdue items thus removing the long-overdue status on the item





## Basic checkout

1. From the home screen, click the *Check Out Items* link. Or, select *Check Out* from the *Circulation* menu in the toolbar. Or, if you are already in a patron's record, you may skip to #3 after selecting the *Check Out* tab.
1. Scan the patron's barcode.
1. If the patron does not have their card, click the [[PatronsSearchForPatrons][Patron Search]] link to retrieve the account by search.
1. Scan the Item Barcode.
1. The check out record appears in the table.
1. Repeat until all materials are checked out.
1. Select a [[Evergreen.CheckOut#Receipt_Options][receipt option]] or click Done to generate a default receipt and close the patron account.

## Checkout with specific due date
1. Before scanning the Item Barcode, click the calendar widget in the [[Evergreen.CheckOut#Date_Options][Date Options]] field
1. Select the desired due date
    * All subsequent loans to the patron will use the same specific due date
    * The date will reset to normal for the next patron
1. Proceed to scan items

### Date Options
#### One time specific due date checkout

If you are changing the due date for a single patron, click the calendar widget and select the date. Once the patron record is closed, the due date will revert to normal.
#### Use specific due date until logout

If all of the day's circulations will use a special due date, use the "until logout" option. The special date will persist for all patrons until the Evergreen session is logeed out.

## Non-cataloged Items Check Out

If your library "checks out" items that are non individually cataloged because they are interested in statistics for these items, but otherwise does not care if the items are returned, the Non-Cataloged Item check out is the option to use. [[Evergreen.ItemsNonCatalogedTypes][Non-cataoged item types]] are predefined, shared by the entire system, and are also used for tracking [[Evergreen.ItemsRecordInHouseUse][in-house use]].

Non-cataloged item check outs cannot be returned, do not become over due, disappear from the account after their "due date", and do not accrue fines. They only display in the [[Evergreen.PatronsItemsOut#Non_Cataloged_Circulations][Items Out > Non-Cataloged Circulations]] list.

   1 Instead of scanning an item barcode, click the down arrow in the Barcode box to open the non-cataloged types list
   1 Select the appropriate type (the box where a barcode would be scanned greyed out), and click Submit
   1 In the pop-up, enter the number of items crculating, click OK
   1 A blank row will appear in the check outs list

## Receipt Options
### Quick Receipt

Clicking Quick Receipt will generate a date due receipt without closing the patron account. The icon next to the Quick Receipt button - either a printer (printed receipt) or an envelope (emailed receipt) - indicates the format of the quick receipt. If a patron has opted in to receiving email date due receipts, the envelope icon will display.

If for any reason the patron wants a different receipt format for the transaction, click the arrow in the Quick receipt box to select for receipt format.
#### Set emailed receipt default

The emailed receipt preference must be manually enabled. Staff can set this in [[Evergreen/Archive.PatronsAccountEdit][Patron Edit]], by checking the "Email checkout receipts by default?" option. The patron must have a valid email address in their account.

Patrons can set this preference from their online account, in the Preferences > Notification section.
---++ Check Out Pre-Cataloged Materials

"Pre-Cataloged materials" are items that do not yet have records in the catalog, but that the library wishes to circulate anyway. Performing a pre-cataloged check out creates a brief record for the purpose of circulation. The item may, or may not, have a barcode sticker.

If the item has a barcode sticker, scan it again to to rule out a mis-scan. Most barcoded items do have records. If the item is filling a hold, it has a valid record.

---++ Check Out Failures

If the copy being scanned in Check Out has a copy status other than available/reshelving or on hold shelf for the check out patron, a Check Out Failure Alert will display. These alerts typically describe the issue, and provide options to override the failure, or to take other actions to clear the copy status and proceed with the check out.
---+++ Copy Not Available: Damaged

---+++ Copy Not Available: Missing

---+++ Copy is in Transit

---+++ Copy Status Lost or Copy Status Lost and Paid

---+++ Item On Holds Shelf

---+++ Open Circulation
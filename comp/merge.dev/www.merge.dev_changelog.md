---
url: "https://www.merge.dev/changelog"
title: "Merge Changelog"
---

Launch entire categories of integrations with the leading Unified API platform

Connect with an integrations expert

[Book a demo](https://merge.dev/get-in-touch)

No thanks

![](https://images.mutinycdn.com/mutiny-assets/client/exit_popup_dummy_close_button_01.png)

Merge’s Cookie Policy

We use cookies to improve your experience on our site. By clicking “Accept”, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Accept all cookies](https://www.merge.dev/changelog#) [Cookie settings](https://www.merge.dev/cookie-settings)

[×](https://www.merge.dev/changelog#)

We use cookies to improve your experience on our site. By using our site, you are agreeing to the collection and use of data as described in our [Privacy Policy](https://www.merge.dev/legal/privacy-policy).

[Cookie Settings](https://www.merge.dev/archive/cookie-settings) [×](https://www.merge.dev/changelog#)

# Changelog

Learn about Merge’s latest integrations and features

[Get email updates](https://www.merge.dev/changelog#)

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/67c55442d866fa4fb8fd09bb_72ebf6b32e8ec0b7d9cd84c5f392228c_Changelog%20hero.avif)

May 30, 2025

https://www.merge.dev/changelog/week-4

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, May 2025

# ✨

## Improvements

##### 💰     Accounting

- Added pagination enhancements for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Netsuite

##### 🤝     ATS

- Added support for modified since filter for faster subsequent syncs for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for CATS
- Added pagination enhancements for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for iCIMS
- Added performance improvements across all models for JobAdder

##### 🏆     CRM

- Added support for cloud based accounts for SugarCRM
- Added mapping enhancements for datetimes for “created\_at” for [POST /notes](https://docs.merge.dev/crm/notes/#notes_create) for Hubspot

##### 🏠     HRIS

- Added mapping enhancements to capture “pay\_rate” and “job\_title” changes in [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Dayforce
- Added support for employees with “start\_date” before 1990 for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Dayforce
- Added support for “Paid Leave” and “Unpaid Leave” as “ACTIVE” for “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Added mapping enhancements to work locations for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for Workday

##### 🎟️     Ticketing

- Added mapping enhancements for “remote\_fields” on [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added support for custom field type “component” for [GET /tickets/remote-field-classes](https://docs.merge.dev/ticketing/tickets/#tickets_remote_field_classes_list) and [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added webhook compatibility for Jira Data Center customers on versions 10+
- Added support for deleted users and added mapping enhancements to “is\_active” for [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Teamwork
- Added support for archived and completed tickets for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Trello
- Added support for collection\_ids in [GET /ticket/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Linear and Trello

# 👨‍💻

## SDK Updates

- Advanced [Java SDK v2.0.0](https://github.com/merge-api/merge-java-client/releases/tag/v2.0.0)

May 21, 2025

https://www.merge.dev/changelog/week-3-may-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, May 2025

# ✨

## Improvements

##### 💰     Accounting

- Added support for new field “type” on Items common model
- Added support for [POST /items](https://docs.merge.dev/accounting/items/#items_create) and [PATCH /items](https://docs.merge.dev/accounting/items/#items_partial_update) for Quickbooks Online

##### 🤝     ATS

- Added performance improvements for faster syncing for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for CATS
- Added mapping enhancements to [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Clockwork
- Added mapping enhancements to subsequent syncs to capture all job updates for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SmartRecruiters

##### 🏆     CRM

- Added support to edit “remote\_fields” in [PATCH /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Hubspot
- Added support for additional remote field class types for [GET /contacts/remote-field-classes](https://docs.merge.dev/crm/contacts/#contacts_remote_field_classes_list) for Salesforce

##### 📁     File Storage

- Added efficiency improvements for initial and subsequent sync for linked account with selective sync for Google Drive
- Added mapping enhancement when users scope is disabled for [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for SharePoint

##### 🏠     HRIS

- Added subsequent sync speed improvements for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list), [GET /employments](https://docs.merge.dev/hris/employments/#employments_list), and [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for 7Shifts
- Added additional fields in “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for ChartHop
- Added mapping enhancements for “start\_date” for rehired employees in [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paychex
- Added mapping enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) and [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Paylocity

##### 🔗     Merge Link

- Added ability to jump straight to Selective Sync screen in Merge Link

May 14, 2025

https://www.merge.dev/changelog/week-2-may-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, May 2025

# 🎨

## Improvements to Merge Dashboard UI

Check out our redesigned dashboard homepage, which now displays the most recent issues, number of billed linked accounts, and the number of linked accounts per integration ordered by usage.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6824e23459180910a876bcec_Merge%20Dashboard%20-%20May%2013.png)

# ✨

## Improvements

##### 💰     Accounting

- Added sync efficiency improvements for [GET /balance-sheets](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list) for Quickbooks Online
- Added support for new field “type” on [GET /items](https://docs.merge.dev/accounting/items/#items_list) for Quickbooks Online
- Added support for POST /items and PATCH /items for Quickbooks Online
- Added sync efficiency improvements for Xero accounts with Attachments scope disabled

##### 🤝     ATS

- Added edge case support for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for UKG Pro Recruiting

##### 🏆     CRM

- Added support to create “remote\_fields” on [POST /accounts](https://docs.merge.dev/crm/accounts/#accounts_create) for Hubspot

##### 📁     File Storage

- Added support for admin authentication for Dropbox
- Enhanced sync speeds & deletion detection for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) & [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Dropbox
- Added support for “checksum” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Dropbox
- Added support for [GET /users](https://docs.merge.dev/filestorage/users/#users_list) & [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for Dropbox

##### 🏠     HRIS

- Added mapping enhancement for “employment\_status” for rehired employees for ADP SFTP
- Added mapping enhancement for “country” for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for ADP Workforce Now
- Enhanced rate limiting logic for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Hibob
- Added mapping enhancement for “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Justworks
- Added support for “termination\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Enhanced rate limiting logic for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paycom
- Added support for “managers” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Payfit
- Added support for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) & [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Payfit
- Added mapping enhancement for “start\_date” for rehired employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP Successfactors
- Added mapping enhancement for mobile\_phone\_number mapping for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Added “EXEMPT” and “NONEXEMPT” enum value mappings for “flsa\_status” for [GET /employments](https://docs.merge.dev/hris/employments/) for UKG Pro

##### 🎟️     Ticketing

- Added support for GET /remote-field-class and “remote\_fields” in [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list), [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create), [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve), [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) and [GET /tickets/meta/patch](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) for Azure DevOps
- Added support for “creator” and mapping enhancements for “collections” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Azure DevOps
- Added support to create tickets with “due\_date”, “parent\_ticket” and “priority” and mapping enhancements for “assignees”, “collections”, and “tags” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Azure DevOps
- Added support to edit  “collections”, “due\_date”, “parent\_ticket”, “priority” and “ticket\_type” and improved error handling for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Azure DevOps
- Added mapping enhancements for “assignee” updates for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira Service Management

May 8, 2025

https://www.merge.dev/changelog/week-1-may-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, May 2025

# 🖇️

## Integrations

Lattice for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/681cfa58f82889fec40d301d_Lattice%20Changelog.png)

# ✨

## Improvements

##### 💰     Accounting

- Added support for “exch\_rate\_type\_id” as an integration parameter for [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create) for Sage Intacct
- Added support for [POST /credit-notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_create)

##### 🤝     ATS

- Added error handling for all answer types for “screening\_question\_answers” for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Ashby

##### 🏆     CRM

- Added support for special characters for [POST /accounts](https://docs.merge.dev/crm/accounts/#accounts_create), [POST /contacts](https://docs.merge.dev/crm/contacts/#contacts_create) and [POST /leads](https://docs.merge.dev/crm/leads/#leads_create) for Salesforce
- Added performance improvements for faster syncs when “remote\_fields” are disabled for [GET /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Salesforce

##### 📁     File Storage

- Added better error messaging and support for larger files for [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_download_retrieve) for Google Drive
- Added performance enhancements when selective sync is enabled for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive
- Added performance enhancements to reduce errors for [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_download_retrieve) for OneDrive
- Added error handling when groups are disabled for [GET /users](https://docs.merge.dev/filestorage/users/#users_list) for SharePoint
- Added authentication validation support for SharePoint to show detailed errors if end users are attempting to connect to an OAuth app that they don’t have permissions for

##### 🏠     HRIS

- Added support for timeoff data older than 6 months for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Hibob
- Added error handling to support a higher link success rate for Paycor
- Added mapping enhancements for “status” for terminated employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Sage HR
- Added support to normalize en\_GB picklist options for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for SAP SuccessFactors
- Added support for more fields in “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Added support for “company\_id” selective sync filter for UKG Pro

##### 🎟️     Ticketing

- Updated from v1 to v2 endpoints for Jira

##### ⚛     Cross-category

- Improvements to PATCH endpoint to correctly return 404 errors when targeting deleted objects

##### 🔗     Merge Link

- Enhancements to loading times for field mapping searches on large Workday accounts
- Resolved an issue causing Field Mappings to be unavailable if the org-level scope isn't enabled

April 30, 2025

https://www.merge.dev/changelog/week-5-april-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, April 2025

# ✨

## Improvements

##### 💰     Accounting

- Updated all Sage integration logos in Merge Link

##### 📁     File Storage

- Added edge case handling to ensure duplicate permission are never created for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive
- Added edge case handling for disabled scopes for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive

##### 🏠     HRIS

- Added support for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Deel
- Added support for “net\_pay”, “gross\_pay”, “earning.amount”, “earning.type”, and “taxes” for [GET /employee-payroll-run](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for Gusto
- Added support for “preferred\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Added support for “provider\_name”, “company\_contribution”, and “employee\_contribution” for [GET /employer-benefits](https://docs.merge.dev/hris/employer-benefits/#employer_benefits_list) for Gusto
- Added support for “effective\_date” and “pay\_frequency” for contractors for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Gusto
- Added support for [GET /pay-groups](https://docs.merge.dev/hris/pay-groups/#pay_groups_list) and [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Gusto
- Added support for “run\_state" for [GET /payroll-run](https://docs.merge.dev/hris/payroll-runs/#payroll_runs_list) for Gusto
- Added support for additional fields in “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Microsoft Entra
- Added support for additional group type “BUSINESS\_UNIT” for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for UKG Pro

##### 🎟️     Ticketing

- Added support for task created events for private tickets and project membership events for Asana
- Added edge case handling for disabled scopes for [GET /collections](https://docs.merge.dev/ticketing/collections/#collections_list) & [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added edge case handling to prevent duplicate tickets in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Trello
- Added support for assignee change event webhooks for Trello

##### 🎮     Merge Dashboard

- Enhanced various UI elements with new brand for consistency
- Enhanced dashboard interface with improved layout and consistent header styling
- Enhanced navigation menu appearance and functionality

##### 🔗     Merge Link

- Improvements to our File Picker Selective Sync flow
- Improvements to the Field Mapping options dropdown when rendering large option sets

April 24, 2025

https://www.merge.dev/changelog/week-4-april-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, April 2025

# 🪄

## Rate-limit management for passthrough requests

Merge has expanded rate limit management to include passthrough requests. Now when you're close to hitting a third-party rate limit, Merge will return a 400 error: “ `Third-party API provider rate limit exceeded. Please try again later.`” as a warning. This helps protect your linked account's functionality and prevents delays when making any passthrough requests.

# 🖇️

## Integrations

FolksHR for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/680b01698accc80e36ac9b58_FolksHR.png)

# ✨

## Improvements

##### 🏆     CRM

- Added support to update “address” and “phone\_number” for [PATCH /contacts](https://docs.merge.dev/crm/contacts/#contacts_partial_update) for Salesforce

##### 📁     File Storage

- Added support for “Super Admin” authentication (higher level access that allows viewing all user files across an organization) for Google Drive, Box and SharePoint
- Added support for “checksum” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive
- Added edge case handling for expired tokens for [GET /users](https://docs.merge.dev/filestorage/users/#users_list) for SharePoint
- Added support for when a file is unshared with the authenticated user to mark as “remote\_was\_deleted” = true for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for SharePoint
- Added support for a group with remote\_id “Company Members” that contains all internal users within an organization for [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for SharePoint

##### 🏠     HRIS

- Added performance enhancements for faster syncs for custom fields for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for HiBob
- Added reliability enhancements for redaction in remote data and logs for Justworks
- Added support for additional fields in “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Added reliability enhancements to prevent syncing non-employees (dependents) for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors

##### 🎟️     Ticketing

- Added support for “access\_level” and “viewers” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [GET /collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Asana
- Added support for user.added, user.changed, user.removed, user.deleted, user.undeleted, project\_membership.added and project\_membership.removed webhook events for Asana
- Added support for “Super Admin” authentication for Asana
- Added support for status “resolved” as “CLOSED” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added support to edit “remote\_fields” with [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ServiceNow
- Added support for OAuth for ServiceNow

##### 🎮     Merge Dashboard

- UX/UI improvements
- Optimized and enhanced certain interface elements

##### 🔗     Merge Link

- Improvements to linking flow by skipping certain screens when only a single option exist
- UI enhancements

April 16, 2025

https://www.merge.dev/changelog/week-3-april-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, April 2025

# 📁

## File Storage integrations: enhanced reliability & performance

We've improved our File Storage category to enhance integration quality. Key updates include more precise permission mapping across providers, expanded webhook coverage for real-time updates, faster sync speeds, and better handling of edge cases to improve data integrity and reliability.

# 🖇️

## Integrations

CoolCare for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6800415cc198eba73fc06f6e_Coolcare%20Changelog.png)

# ✨

## Improvements

##### 💰     Accounting

- Added support for additional fields in “remote\_data” for [GET /company\_info](https://docs.merge.dev/accounting/company-info/#company_info_list) for Quickbooks Online

##### 🤝     ATS

- Added mapping enhancement for “attachments” on [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for BambooHR

##### 🏆     CRM

- Added support for updating “address” in [PATCH /accounts](https://docs.merge.dev/crm/accounts/#accounts_partial_update) for Salesforce

##### 📁     File Storage

- Added performance enhancements for faster syncs for Box
- Added support for permissions on file created and folder created webhook events for Box
- Added improved error handling for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive
- Added support for link validation (preventing non admins from linking with admin authentication) for SharePoint

##### 🏠     HRIS

- Added support for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list), [GET /employments](https://docs.merge.dev/hris/employments/#employments_list), [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) and [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for CezanneHR
- Added mapping enhancements to prevent duplicate objects for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for Hibob
- Added performance enhancements for faster syncs for [GET /timesheet-entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list) for UKG Ready

##### 🎟️     Ticketing

- Added support to create and update “attachments” in [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update)
- Updated “pending” status to “IN\_PROGRESS” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Zendesk

##### 🎮     Merge Dashboard

- Ability to enable SFTP for select integrations in Dashboard

##### 🔗     Merge Link

- Ability to configure which permissions are available in Merge Link

April 9, 2025

https://www.merge.dev/changelog/week-2-april-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, April 2025

# 🤖

## Announcing our Merge Model Context Protocol (MCP)!

MCP is quickly becoming the go-to standard for connecting large language models (LLMs) to external data sources. This is why we’re so excited to announce Merge MCP!

Merge Model Context Protocol (MCP) allows your AI assistant to quickly and intelligently take real actions in your customers’ third-party platforms — whether that’s updating tickets, reading files, or creating journal entries.

Through just a few lines of code, Merge MCP enables your AI Agent to access hundreds of tools (actions) via a single MCP server.

Check out our [docs](https://docs.merge.dev/basics/mcp/) and our [GitHub](https://github.com/merge-api/merge-mcp) on how to implement Merge MCP!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67f69d70697b53f42d0660be_Merge_MCP_tools_optimized.png)

# ✨

## Improvements

##### 💰     Accounting

- Added mapping enhancements to “remote\_fields” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Sage Intacct

##### 📁     File Storage

- Added support for “checksum” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Box, Google Drive, and SharePoint
- Added mapping enhancements for unshared files for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive
- Added mapping enhancements for “drive\_id” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) and [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Google Drive
- Added performance enhancements for permissions for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for SharePoint

##### 🏠     HRIS

- Added mapping enhancements for “termination\_date” for Employees for ADP Workforce Now SFTP
- Added support for work locations for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for Microsoft Entra ID
- Added mapping enhancements to “ethnicity” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Hibob
- Migrated all endpoints from v1 to v2025 for Factorial

##### ⚛     Cross-category

- Added edge case support for improved sync performance across all integrations

##### 🔄     Syncing data

- Improved error visibility: GET /sync-status now clearly displays last\_sync\_result for relevant error codes

##### 📄     Docs

- Updated documentation for Async POST operation webhook behavior
- Improved clarity for unsupported fields under “Field Support by Integration”

April 3, 2025

https://www.merge.dev/changelog/week-1-april-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, April 2025

# ✨

## Improvements

##### 💰     Accounting

- Added performance enhancements to [GET /contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Xero

##### 🤝     ATS

- Added mapping enhancements to “source” for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for UKG Pro Recruiting

##### 📁     File Storage

- Added validation and error messaging in Merge Link for admin and non-admins authentication for Google Drive
- Added subsequent sync performance enhancements for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) & [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Google Drive
- Added mapping enhancements and error handling for ‘parent\_folder” for [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for SharePoint

##### 🏠     HRIS

- Added performance enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paycom
- Added support for “start\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for TriNet HR Platform

##### 🎟️     Ticketing

- Added mapping enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Jira Data Center
- access\_level field now available on [Tickets](https://docs.merge.dev/ticketing/tickets/)

##### 🔗     Merge Link

- UI / UX enhancements when Link is reopened after an account is successfully linked
- UI enhancements to [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) screens

‍

March 26, 2025

https://www.merge.dev/changelog/week-4-march-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, March 2025

# ✨

## Improvements

##### 💰     Accounting

- Added mapping enhancements to “remote\_data” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Netsuite
- Added performance enhancements for [GET /general-ledger-transactions](https://docs.merge.dev/accounting/general-ledger-transactions/#general_ledger_transactions_list) for Quickbooks Online

##### 🏆     CRM

- Added mapping enhancements to “remote\_fields” for [PATCH /accounts](https://docs.merge.dev/crm/accounts/#accounts_partial_update) for Hubspot

##### 📁     File Storage

- Added performance enhancements for faster subsequent syncs for [GET /drives](https://docs.merge.dev/filestorage/drives/#drives_list), [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) and [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive
- Added performance enhancements for faster permission syncing for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for SharePoint

##### 🏠     HRIS

- Added mapping enhancements for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Hibob
- Added mapping enhancements for “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro

##### 🎟️     Ticketing

- Added mapping enhancements to the “modified\_at” filter for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added support for “remote\_data” for [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Jira
- Added support for “remote\_fields” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list), [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create), and [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira Data Center
- Added support for [GET /tickets/remote-field-classes](https://docs.merge.dev/ticketing/tickets/#tickets_remote_field_classes_list) for Jira Data Center
- Added support for project and cycle (normalized to collections) webhook events for Linear
- Added support to restore deleted issues, projects, cycles and comments for Linear
- Added support for “access\_level” and “creator” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Linear
- Added support for “access\_level” for [GET /collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Linear
- Added support for [GET /tickets/viewers](https://docs.merge.dev/ticketing/tickets/#tickets_viewers_list) and [GET /collections/viewers](https://docs.merge.dev/ticketing/collections/#collections_viewers_list) for Linear (Beta)
- Added support for additional enums for “status” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Rally
- Added support for “due\_date”, “priority”, additional “ticket\_type” enums and added mapping enhancements to “collections”, “parent\_ticket” and “status” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Rally
- Added support for “due\_date”, “priority”, additional “ticket\_type” enums and added mapping enhancements to “collections”, “names”, “parent\_ticket”, “status” and “tags” for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Rally
- Added mapping enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) and [GET /tickets/meta/patch](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) for Rally
- Added support for additional field\_types (picklists, relations, and arrays) for [GET /tickets/remote-field-classes](https://docs.merge.dev/ticketing/tickets/#tickets_remote_field_classes_list) for ServiceNow
- Added support for “remote\_fields” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for ServiceNow
- Added mapping enhancements to support additional webhooks events for Wrike
- Added support for “ticket\_url” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Zoho Desk

##### 🎮     Merge Dashboard

- UX improvements for configuring [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) filters at the Linked Account level
- Improvements to [login](https://app.merge.dev/login) and [signup](https://app.merge.dev/signup) pages, including for mobile users

##### 🔄     Syncing data

- Improvement to [Deleted Data Detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection) for multiple integrations (incl., BambooHR, Workday, SageHR)

# 👨‍💻

## SDK Updates

- Advanced Node [v1.1.6](https://github.com/merge-api/merge-node-client/releases/tag/v1.1.6)

‍

March 13, 2025

https://www.merge.dev/changelog/week-2-march-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, March 2025

# ✨

## Improvements

##### 💰     Accounting

- Added support for “inclusive\_of\_tax” for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) and [PATCH /invoices](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) for Quickbooks Online
- Added mapping enhancement for “transaction\_date” for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Quickbooks Online

##### 📁     File Storage

- Added support for “order\_by” query parameter for [GET /files](https://docs.merge.dev/filestorage/files/#files_list)
- Added support for drive created, updated, and deleted webhooks for Google Drive

##### 🏠     HRIS

- Added mapping enhancements for “personal\_email” and “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Dayforce
- Added support for “gross\_pay”, “net\_pay” and “taxes” for [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for UKG Ready

##### 🎟️     Ticketing

- Added support for milestones in [GET /collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Github Issues
- Added support for “parent\_ticket” in [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Github Issues
- Added support for “remote\_data” in [GET /tags](https://docs.merge.dev/ticketing/tags/#tags_list) for Github Issues
- Added support for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Github Issues
- Added support for consumers as “contact” in [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for ServiceNow
- Added support for “ticket\_type” and “creator” in [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Wrike
- Added support for additional enums for “status” in [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Wrike
- Added support for “ticket\_type” in [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Wrike
- Added support for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Wrike

##### ⚛️     Cross-category

- Improved experience when requesting data that has been marked as [shell](https://help.merge.dev/en/articles/9713879-what-is-shell-data-filtering) or [deleted](https://help.merge.dev/en/articles/5392795-deleted-data-detection)

February 27, 2025

https://www.merge.dev/changelog/week-4-february-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, March 2025

# 🖇️

## Integrations

HRWorks for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67c10c7edfa0a63b7ec959a8_HRWorks.webp)

# ✨

## Improvements

##### 💰 Accounting

- Added support for “sub\_total” for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Netsuite

##### 📁     File Storage

- Added mapping enhancements to [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Dropbox
- Added enhancements to deleted data for subsequent syncs for Google Drive
- Added mapping enhancements to “name” for [GET /drives](https://docs.merge.dev/filestorage/drives/#drives_list) for SharePoint
- Added performance enhancements for subsequent syncs for [GET /users](https://docs.merge.dev/filestorage/users/#users_list) for SharePoint

##### 🏠     HRIS

- Added enhancements to “date\_of\_birth” and “ssn” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Run
- Added enhancements to the BambooHR linking flow for EU

##### 🎟️     Ticketing

- Adding mapping enhancements for “collections” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana
- Added mapping enhancement for “due\_date” timezone for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) & [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ClickUp
- Added mapping enhancements for [POST /comments](https://docs.merge.dev/ticketing/comments/#comments_create) for Github Issues
- Added support to update “priority” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira
- Added support for remote fields of type user in [GET /remote-field-classes](https://docs.merge.dev/ticketing/tickets/#tickets_remote_field_classes_list) for Jira
- Added support for “remote\_fields” in [GET /tickets/meta/patch](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) for Jira
- Added edge case handling for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira Data Center

##### 🎮     Merge Dashboard

- Improvements to handling of special characters in [logs](https://app.merge.dev/logs/api-requests) search. Applies to all logs pages, including Linked Account logs
- Improvements to UX when configuring [Integration settings](https://app.merge.dev/integrations/hris)
- UI updates to Linked Account Selective Sync page

##### 🔗     Merge Link

- Improvements to [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) for File Storage
- Improvements to data permission screens

# 👨‍💻

## SDK Updates

- Advanced C# [v1.0.2](https://github.com/merge-api/merge-csharp-client/releases/tag/1.0.2)

‍

February 21, 2025

https://www.merge.dev/changelog/week-3-february-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, February 2025

# 💰

## New Accounting Common Models: Payment Terms and Payment Methods

We are excited to announce two new accounting Common Models that support both bill pay (AP automation) and receivables product (AR Automation). [Payment Terms](https://docs.merge.dev/accounting/payment-terms/) and [Payment Methods](https://docs.merge.dev/accounting/payment-methods/) will enhance existing transaction common models with information about how and when payments should be made.

# 📁

## Increased load speed for File Picker

Our team is constantly working on improving the user experience, and a major part of that is speed and efficiency. We have made large improvements to our SharePoint integration, and now it loads 7× faster in our [File Picker](https://docs.merge.dev/filestorage/file-picker/)! Try it out today!

# ✨

## Improvements

##### 🤝     ATS

- Added mapping enhancements to [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Ashby
- Added support for [GET /offers](https://docs.merge.dev/ats/offers/#offers_list) for iCIMs

##### 📁     File Storage

- Added support for “size” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive
- Added mapping enhancements for “parent\_folder” for [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for SharePoint

##### 🏠     HRIS

- Added mapping enhancements for “managers” for Employees for ADP Workforce Now SFTP
- Added performance enhancements for [GET /timesheet-entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list) for BambooHR
- Added mapping enhancements to “employment\_type” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro
- Added support for [GET /bank-info](https://docs.merge.dev/hris/bank-info/#bank_info_list) for Workday

##### 🎟️     Ticketing

- Added support for remote fields of type user for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added support to edit remote fields in [PATCH /ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) s for Jira
- Added support for [POST /attachments](https://docs.merge.dev/ticketing/attachments/#attachments_create) for Intercom
- New query param available for [GET /tickets/remote-field-classes](https://docs.merge.dev/ticketing/tickets/#tickets_remote_field_classes_list) \- the response can now be filtered by a list of remote-field-class IDs

##### ⚛     Cross-category

- Linked Accounts in IDLE status can now be seen via API on the [/linked-accounts](https://docs.merge.dev/hris/linked-accounts/#linked_accounts_list) and [/account-details](https://docs.merge.dev/hris/account-details/#account_details_retrieve) endpoints

##### 🎮     Merge Dashboard

- UI improvements to [Selective Sync](https://app.merge.dev/configuration/selective-sync/ticketing) page for disabled filters

##### 🔗     Merge Link

- Improvements to type-ahead search when [selecting Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/for-linked-account/) options

##### 🔄     Syncing data

- Improvements to [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) option generation
- Improvements to calculation of sync status for [ADP WFN](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/) [Linked Accounts](https://app.merge.dev/linked-accounts/accounts)

# 👨‍💻

## SDK Updates

- Advanced [Node v.1.1.5](https://github.com/merge-api/merge-node-client/releases/tag/v1.1.5)
- Advanced [GO v1.1.1](https://github.com/merge-api/merge-go-client/releases/tag/v1.1.1)

February 11, 2025

https://www.merge.dev/changelog/week-2-february-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, February 2025

# 🎉

## Formal partnership with Gusto

We’re thrilled to announce that we’ve entered into a formal partnership with Gusto, a leading HR and payroll solution for SMBs!

Learn how Merge can help you build an approved Gusto integration as well as how your product can use a customer-facing, API-based Gusto integration on [our blog](https://www.merge.dev/blog/gusto-partnership).

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67acd05235f184a944e67407_Gusto%20Merge%20Partnership%20.webp)

# 🖇️

## Integrations

ADP Decidium for HRIS and Crelate for ATS are now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67ac3565d877fce1bc7fc4fd_ADP%20Decidium%20%26%20Crelate.webp)

# ✨

## Improvements

##### 💰     Accounting

- Added enhancements to [deletion detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection) for general ledger transactions for NetSuite

###### 🤝     ATS

- Added mapping enhancements to “remote\_data” for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for JobAdder

##### 📁     File Storage

- Added enhanced error messaging for [POST /files](https://docs.merge.dev/filestorage/files/#files_create) for OneDrive
- Added performance enhancements for subsequent syncs for SharePoint

##### 🏠     HRIS

- Added mapping enhancements for historical employments for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Dayforce
- Added support for multiple companies in linking flow for Insperity
- Added mapping enhancements to prevent shell employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Added mapping enhancements for [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for Paylocity
- Added mapping enhancements for [GET /pay-groups](https://docs.merge.dev/hris/pay-groups/#pay_groups_list) for Trinet
- Added mapping enhancements for “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### 🎟️     Ticketing

- Added mapping enhancements for “assignees” for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Asana
- Added support for “ticket\_type” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana
- Added mapping enhancements to [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) to correctly mark tickets as closed for ClickUp
- Added mapping enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) & [GET /tickets/meta/patch](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) to only return available status enums for ClickUp
- Added support for [GET /tickets/meta/patch](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) for Liner
- Added mapping enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) to only return available status and priority enums for Linear
- Added mapping enhancements to required fields for [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Zendesk
- Added mapping enhancements for “status” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) & [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Zendesk
- Added mapping enhancements to “name” for updateCard webhook events for Trello

##### ⚛️     Cross-category

- Linked Account ID now available in response for [GET /account-token/{public\_token}](https://docs.merge.dev/hris/account-token/#account_token_retrieve)

##### 📄     Docs

- Revamped [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) section, including new page for [Advanced mapping](https://docs.merge.dev/supplemental-data/field-mappings/advanced-mapping/)

##### 🔄     Syncing data

- Added support for edge cases in syncs for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/)
- Added support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/)
- Added support for edge cases when generating [remote data](https://docs.merge.dev/supplemental-data/remote-data/) for [Workday](https://docs.merge.dev/integrations/hris/workday/sync-frequencies/)

# 👨‍💻

## SDK Updates

- Advanced Python [v1.1.4](https://github.com/merge-api/merge-python-client/releases/tag/v1.1.4)
- Advanced C# [v1.0.1](https://github.com/merge-api/merge-csharp-client/releases/tag/1.0.1)

February 6, 2025

https://www.merge.dev/changelog/week-1-february-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, February 2025

# 🖇️

## Integrations

Dayforce for ATS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67a5453a5260e48291f3c723_Dayforce.webp)

# ✨

## Improvements

##### 🤝     ATS

- Added mapping enhancement for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Greenhouse
- Added mapping enhancement for “remote\_data” for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Oracle Taleo

##### 🏆     CRM

- Added “title” as integration parameter for [POST /notes](https://docs.merge.dev/crm/notes/#notes_create) for Salesforce

##### 🏠     HRIS

- Added support for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for ADP Run
- Adding mapping enhancement for “employment\_status” for Employees for ADP SFTP
- Adding mapping enhancement for “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added mapping enhancement for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for HaileyHR
- Added mapping enhancement for “first\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Increased rate limits for Paylocity
- Added mapping enhancement to “date\_of\_birth” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Personio
- Added support for “start\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Rippling
- Added mapping enhancement for “employment\_type” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro

##### 🎟️     Ticketing

- Added support for query parameter “teams” on [GET /users](https://docs.merge.dev/ticketing/users/#users_list)
- Added linking flow enhancements to Aha!
- Added authentication enhancements to Linear

January 29, 2025

https://www.merge.dev/changelog/week-4-january-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, January 2025

# ✨

## Improvements

##### 💰     Accounting

- Added support for "bill\_reference\_number” in “integration\_params” for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Netsuite
- Added support for “base\_location\_remote\_id” in “integration\_params” for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Sage Intacct
- Added support for “account\_type” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Sage Intacct

##### 🤝     ATS

- Added mapping enhancements to [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Gem

##### 🏠     HRIS

- Added support for additional enum mappings for “ethnicity” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added mapping enhancement to “display\_full\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for HaileyHR
- Added performance enhancements to “groups” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Okta
- Added mapping enhancements for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for SAP SuccessFactors

##### 🎟️     Ticketing

- Added support for “ticket\_type” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana
- Added mapping enhancements for “ticket\_url” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira Data Center
- Added mapping enhancements for “parent\_ticket” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira Data Center
- Added support for [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) for Linear
- Added support for “collection\_id” and “team\_merge\_id” as query parameters for [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Linear
- Added mapping enhancement to “ticket\_type” for [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Zendesk
- Added mapping enhancements to account for deleted users in [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Zoho Desk

##### 🎮     Merge Dashboard

- [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) UI updates

##### 🔗     Merge Link

- [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) UI updates

##### 📄     Docs

- Updates to File Picker page
- General Docs UI updates

##### 🔄     Syncing data

- Added support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)

January 24, 2025

https://www.merge.dev/changelog/week-3-january-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, January 2025

# 🖇️

## Integrations

‍ [Leapsome](https://www.merge.dev/integrations/leapsome) for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6792ee400991c8a9d7226d4b_6792edfbbc09ffcf5623d6e9_Leapsome.webp)

# ✨

## Improvements

##### 💰     Accounting

- Added mapping enhancement to “general\_ledger\_transaction\_lines” for [GET /general-ledger-transactions](https://docs.merge.dev/accounting/general-ledger-transactions/#general_ledger_transactions_list) for Quickbooks Online
- Added mapping enhancement to “account” for [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Sage Intacct
- Added query param filters for Invoice `number` and `status` on [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list)
- Added query param filter for Account `name` on [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list)
- Added query param filter for Tracking Category `name` on [GET /tracking-categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list)
- Added query param filter for Tax Rate `name` on [GET /tax-rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list)

##### 🤝     ATS

- Added mapping enhancements [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Manatal

##### 🏠     HRIS

- Added support for “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Dayforce
- Added edge case handling for [GET /timesheet-entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list) for Paycom
- Added support for “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Planday
- Added mapping enhancements to Employees and Employments for SAP SuccessFactors SFTP
- Added mapping enhancement to “first\_name” and “last\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Added support for “parent\_group” for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for SAP SuccessFactors
- Added mapping enhancement for re-hired employees in [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### 🎟️     Ticketing

- Added mapping enhancement when updating “assignee” for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Asana
- Added mapping enhancement when posting “status” in [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Zendesk
- Added mapping enhancement when updating “status” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Zendesk

##### 🔗     Merge Link

- Improvements to permissions editing screen

##### 📄     Docs

- Updates to [Supplemental Data: Overview](https://docs.merge.dev/supplemental-data/overview/) page

##### 🔄     Syncing data

- Improvements to [3rd party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) for Asana
- Added support for edge cases in syncs for [Justworks](https://docs.merge.dev/integrations/hris/justworks/)
- Added support for edge cases when [creating Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) in [Jira](https://docs.merge.dev/integrations/ticketing/jira/)

# 👨‍💻

## SDKs

- Advanced [Node v1.1.2](https://github.com/merge-api/merge-node-client/releases/tag/v1.1.2)
- Advanced [Ruby v1.0.0](https://github.com/merge-api/merge-ruby-client/releases/tag/v1.0.0)
- Advanced [Java v1.1.1](https://github.com/merge-api/merge-java-client/releases/tag/v1.1.1)
- Advanced [GO v1.1.0](https://github.com/merge-api/merge-go-client/releases/tag/v1.1.0)

January 14, 2025

https://www.merge.dev/changelog/week-2-january-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, January 2025

# ✨

## Improvements

##### 💰     Accounting

- Enhanced linking flow for Microsoft Dynamics Business Central
- Added mapping enhancement to [GET /vendor-credits/meta/post](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_meta_post_retrieve) for Quickbooks Onlines
- Added mapping enhancement for [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbookes Online
- Added support for inactive account for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Zoho Books

##### 🤝     ATS

- Added performance enhancements to [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) and [GET /screening-questions](https://docs.merge.dev/ats/screening-questions/#jobs_screening_questions_list) for Breezy
- Added mapping enhancement to “attachments” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Jobdiva
- Added performance enhancements to [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Lever
- Added mapping enhancement to [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for UKG Pro
- Added support for filters to [GET /users](https://docs.merge.dev/ats/users/#users_list) to supplement “remote\_data” with custom objects for SAP SuccessFactors

##### 📁     File Storage

- Added mapping enhancements to automatic webhooks for Google Drive

##### 🏠     HRIS

- Enhanced error handling for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added pagination enhancement to Sage People
- Added support for filters to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) to supplement “remote\_data” with custom objects for SAP SuccessFactors

##### 🎟️     Ticketing

- Added mapping enhancements for “descriptions” for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Azure DevOps
- Added mapping enhancements when updating “priority” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Linear

##### 📄     Docs

- UI updates for [Webhooks Overview](https://docs.merge.dev/basics/webhooks/overview/) page

##### 🔗     Merge Link

- UX improvements for [SFTP](https://help.merge.dev/en/articles/9054729-secure-file-transfer-protocol-sftp) linking flow
- Added support for edge cases when linking [Jira](https://docs.merge.dev/integrations/ticketing/jira/sync-frequencies/) accounts

##### 🔄     Syncing data

- Added support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)
- Added support for edge cases in syncs for [Justworks](https://docs.merge.dev/integrations/hris/justworks/sync-frequencies/)
- Improvements to Common Model synced [Webhook](https://app.merge.dev/configuration/webhooks/emitters) calculation during initial syncs
- Improvements to rate limit error messaging for POST endpoints
- Improvements to error messaging for [async passthrough](https://docs.merge.dev/hris/async-passthrough/#async_passthrough_create)
- Improved detection of updates to effective\_date on Employments for [ADP WFN](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/)

January 6, 2025

https://www.merge.dev/changelog/week-1-january-2025

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, January 2025

# ✨

## Improvements

##### 💰     Accounting

- Added support for [GET /general-ledger-transactions](https://docs.merge.dev/accounting/general-ledger-transactions/#general_ledger_transactions_list) in GA for Netsuite and Quickbooks Online and in beta for Sage Intacct and Xero
- Added support for a new field “CreditNoteApplyLines” on [GET /credit-notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) and “VendorCreditApplyLines” [GET /vendor-credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for NetSuite, Quickbooks Online, Sage Intacct, and Xero
- Added support for [POST /credit-notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_create) and [POST /vendor-credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_create) for NetSuite, Quickbooks Online, Sage Intacct, and Xero
- Enhanced error messaging for [GET /expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Quickbooks
- Enhanced error messaging for [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Sage Intacct
- Added mapping enhancements to “email\_addresses”, “is\_customer” and “is\_supplier” for [GET /contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Sage Intacct

##### 🤝     ATS

- Added mapping enhancements for “remote\_data” for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Ashby
- Added mapping enhancements to [POST /candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for Ashby
- Added mapping enhancements for [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Enhanced rate limits for Jobscore

##### 📁     File Storage

- Added performance enhancements to file picker for Google Drive
- Added support for “child\_groups” for [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for OneDrive
- Enhanced error messaging for [POST /files](https://docs.merge.dev/filestorage/files/#files_create) for OneDrive
- Enhanced read only non-admin authentication for SharePoint

##### 🏠     HRIS

- Enhanced header normalization for ADP SFTP and Manual CSV Uploads
- Added support for time off, benefits, and employer benefits models for ADP SFTP
- Enhanced managers, preferred names, and inactive employees for the employee model for ADP SFTP
- Added support for deletion detection for ADP SFTP
- Enhanced end user help guides for ADP SFTP
- Added mapping enhancement when employees unenroll from benefits for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Enhanced “modified\_at” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Okta
- Added rate limit enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) and [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Paycom
- Added mapping enhancements for “dependents” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors

##### 🎟️     Ticketing

- Updated required fields and enhanced error messaging for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Asana
- Added mapping enhancements to automatic webhooks for Linear

##### 🔄     Syncing data

- Added support for edge cases when resetting rate limits for [Oracle Taleo](https://docs.merge.dev/integrations/ats/oracle-taleo/sync-frequencies/)
- [Integration-wide Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/create-field-mapping/across-an-integration/) available for [SmartRecruiters](https://docs.merge.dev/integrations/ats/smartrecruiters/)

##### 🎮     Merge Dashboard

- General UI updates to [API keys page](https://app.merge.dev/keys)
- Updated pop-up screens for [Magic Link](https://docs.merge.dev/guides/magic-link/)
- [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account) now fills in and displays the base URL dynamically
- Improvements when moving to a paid plan; paused linked accounts automatically unpause now after upgrading


December 24, 2024

https://www.merge.dev/changelog/week-4-december-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, December 2024

# 🗾

## Your customers can now map advanced field mappings in Merge Link

Your customers can now create and manage [advanced field mappings](https://help.merge.dev/en/articles/9269164-advanced-field-mapping-with-jmespath) themselves within Merge Link, making it easier to handle any complex mappings. This feature is currently in beta, so if you're interested in getting early access, please reach out to your Customer Support Manager.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/676a145eee17851a5aa71dbb_676a1437b339c28d79478870_Field%2520Mapping%2520Advanced%2520Mapping.webp)

# 🎟️

## Normalized live requests for ticketing

Sometimes, your customers may need to immediately access data from their third-party ticketing platforms, meaning they can’t wait for the initial sync to be completed.

With our new **Normalized Live Requests** feature, customers can instantly access normalized ticketing data in your product.

This feature is currently in beta for our ticketing category. To gain access, please contact your Customer Support Manager.

# 🤝

## Support for write screening question responses

We now support writing screening question answers across key ATS integrations under the [POST /application](https://docs.merge.dev/ats/applications/#applications_create) Common Model. This allows you to capture and save responses to custom screening questions from job applications directly into your customers' ATS, ensuring seamless data integration for your hiring workflows.

We currently support Ashby, Breezy, JazzHR, Lever, SAP, SmartRecruiters, Teamtailor, UKG Pro Recruiting, Workable and Workday.

# 🖇️

## Integrations

[iSolved](https://www.merge.dev/integrations/isolved) for HRIS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/676a145eee17851a5aa71dc0_676a138aeaa02982a52d598c_iSolved.webp)

# ✨

## Improvements

##### 💰     Accounting

- Added support to [PATCH /invoices](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) with “exchange\_rate” for Quickbooks

##### 🤝     ATS

- Added mapping enhancement to [POST /activities](https://docs.merge.dev/ats/activities/#activities_create) for JobAdder
- Added performance enhancements to [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Recruiterflow
- Added support for [GET /job-postings](https://docs.merge.dev/ats/job-postings/#job_postings_list) for SmartRecruiters
- Added mapping enhancement to “status” on [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Added mapping enhancement to “remote\_data” on [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Teamtailor
- Added edge case handling to [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) with “attachments” for Workday

##### 🏆     CRM

- Added mapping enhancement to “start\_time” and “end\_time” for [POST /engagements](https://docs.merge.dev/crm/engagements/#engagements_create) for Hubspot
- Added support to [POST /engagements](https://docs.merge.dev/crm/engagements/#engagements_create) with “contacts” for Hubspot and Pipedrive
- Added performance enhancements to [GET /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Salesforce
- Added edge case handling for [PATCH /accounts](https://docs.merge.dev/crm/accounts/#accounts_partial_update) for Salesforce

##### 📁     File Storage

- Added support for new field “child\_groups” on [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for Google Drive & SharePoint
- Added mapping enhancements to [GET /users](https://docs.merge.dev/filestorage/users/#users_list) and “users” on [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for Google Drive
- Added performance enhancements for initial syncs for Google Drive
- Added mapping enhancement “remote\_id” for [GET /groups](https://docs.merge.dev/filestorage/groups/#groups_list) for SharePoint

##### 🏠     HRIS

- Added mapping enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added support for “display\_name” and “preferred\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Employment Hero
- Added support for “termination\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Added mapping enhancement to “start\_date” on [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Trinet HR Platform

##### 🎟️     Ticketing

- Added mapping enhancements to [PATCH /tickets/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) with “priority” for ClickUp
- Added support for supported “status” enums for [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) and [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for ClickUp
- Added performance enhancements to [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list) for ServiceNow

##### 🎮     Merge Dashboard

- General UI improvements to [logs,](https://app.merge.dev/logs/api-requests) [Settings/Profile](https://app.merge.dev/profile) page, [Issues,](https://app.merge.dev/issues) [Billing](https://app.merge.dev/billing) and [Webhooks](https://app.merge.dev/configuration/webhooks/emitters)
- Improved small screen support when configuring [Field Mappings for Linking Accounts](https://docs.merge.dev/supplemental-data/field-mappings/create-field-mapping/for-linked-account/)
- Updates to the way “Linked” is counted; [Linked Account count](https://app.merge.dev/linked-accounts/accounts) now subtracts “Idle” accounts

##### 📄     Docs

- General UI improvements across all pages
- Added flags for when 3rd parties lack support Merge endpoints (e.g., Microsoft Dynamics for [POST /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_create))

##### 🔄     Syncing data

- Improvements to Deleted Data Detectionlogic
- Added support for edge cases when syncing [Custom Objects](https://app.merge.dev/configuration/custom-objects)
- Improvements to Linked Account [rate limiting](https://docs.merge.dev/basics/rate-limits/) logic
- Improved support for syncing custom fields from [BambooHR](https://docs.merge.dev/integrations/hris/bamboohr/) for [Field Mappings](https://app.merge.dev/configuration/field-mappings/target-fields)

December 17, 2024

https://www.merge.dev/changelog/week-3-december-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, December 2024

# 👥

## New ticketing Common Model: Roles

We’re excited to announce support for pulling user roles across 24 ticketing integrations! You can now easily access a user’s role — including their role name, actions, and access permissions within the ticketing system — all through the [Roles Common Model](https://docs.merge.dev/ticketing/roles/).

This ensures that companies building AI search features that need ticketing data can restrict search results to users with the appropriate permissions. Additionally, the addition of Roles more comprehensively supports user access review use cases needed by security and compliance management companies.

# 🖇️

## Integrations

[Flatchr](https://www.merge.dev/integrations/flatchr) for ATS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6760bfefb0edea726b51e21e_6760bfcb50eb69ac1ee5554d_Flatchr%2520Changelog.webp)

# ✨

## Improvements

##### 💰     Accounting

- Added mapping enhancement to “account\_type” for [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create) for NetSuite
- Added support to custom segments as “remote\_fields” for NetSuite
- Added mapping enhancement to “name” for [GET /tax-rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Quickbooks Online

##### 🤝     ATS

- Added support for “modified\_at” selective sync filter for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) and [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for iCIMS and UKG Pro Recruiting
- Added mapping enhancements to [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for JobScore

##### 🏆     CRM

- Added mapping enhancements to “stage” on [POST /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_create) for Salesforce

##### 🏠     HRIS

- Added mapping enhancement for “job\_title” on [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for BambooHR
- Added mapping enhancement to support additional enums for “employment\_status” on [GET /employee](https://docs.merge.dev/hris/employees/#employees_list) for IntelliHR
- Updated all endpoints from v0.1 to v1.0 for Oyster HR
- Enhanced edge case handling for [GET /benefits](https://docs.merge.dev/hris/benefits/#benefits_list) for Paychex
- Added support for additional enums for “employment\_status” for [Employee](https://docs.merge.dev/hris/employees/) for Workday SFTP
- Added mapping enhancement to support additional enums for “employment\_status” on [GET /employee](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro

##### 🎟️     Ticketing

- Added support for [GET /roles](https://docs.merge.dev/ticketing/roles/#roles_list) and “roles” on [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Azure Devops, ClickUp, Gitlab, Jira, Jira Service Management, Linear, Salesforce Service Cloud, Trello, and Wrike
- Added mapping enhancement for [PATCH /ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) with “status” for Jira
- Added mapping enhancements to [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Linear
- Added performance enhancement for [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list) for ServiceNow

##### 🎮     Merge Link & Dashboard

- UX improvements to managing webhooks for integrations which support [automatic webhook setup](https://docs.merge.dev/basics/webhooks/third-party-webhooks/)
- UI improvements to [Issues page](https://app.merge.dev/issues?status=ONGOING)
- General UI improvements to [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) pages
- UI improvements to “Admin role required” screen
- [Test Linked Accounts](https://app.merge.dev/linked-accounts/test-accounts?&is_test_account=true) are now, by default, able to utilize either production or sandbox instances of Merge credentials

##### 🔄     Syncing data

- Improved pagination logic for [ServiceNow](https://docs.merge.dev/integrations/ticketing/servicenow/) on [GET /tickets/live-search](https://help.merge.dev/en/articles/10226830-live-search-for-ticketing)
- Improved logic for updating modified\_at of objects for [UKG Pro](https://docs.merge.dev/integrations/hris/ukg-pro/)

December 10, 2024

https://www.merge.dev/changelog/week-2-december-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, December 2024

# 🔁

## Merge supports idempotency for accounting integrations

With idempotency, Merge allows you to safely retry POST requests without creating duplicate records. This allows for more resilient, scalable integrations, minimizing duplicate requests and supporting asynchronous processing for heavier tasks.

How it works:

- Use an idempotency key with each POST request
- If the same key is reused within 24 hours, no new request is processed — instead, the original response is returned instantly

You can learn more [here](https://docs.merge.dev/basics/idempotency/). This feature currently is in beta so please reach out to your account representative or [contact us](mailto: support@merge.dev) for more information.

# ✨

## Improvements

##### 💰     Accounting

- Added integration parameter to support to linking attachments to bills for [POST /attachments](https://docs.merge.dev/accounting/attachments/#attachments_create) for Quickbooks Online
- Enhanced [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) line items with remote fields for Netsuite

##### 🤝     ATS

- Added support for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list), [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list), [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Gem
- Enhanced error messaging for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Bullhorn
- Enhanced error handling for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Bullhorn

##### 🏆     CRM

- Added support for archived users on [GET /users](https://docs.merge.dev/crm/users/#users_list) for Hubspot

##### 🏠     HRIS

- Added performance enhancements on [GET /timesheet-entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list) for Personio
- Added support for “country” selective sync filter on [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Enhanced “remote\_data” on [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for UKG Pro

##### 🎟️     Ticketing

- Added support for German enum values for “status” on [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira Service Cloud
- Enhanced authentication and linking for Teamwork
- Added support for [GET /roles](https://docs.merge.dev/ticketing/roles/#roles_list) and “roles” on [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Basecamp, Github Issues, Help Scout, Intercom, ServiceNow, and Zoho Desk
- Enhanced sync performance for [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list) for Zendesk

##### 🎮     Merge Link & Dashboard

- UI / UX enhancements for [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) pages
- UI / UX enhancements for [Linked Account](https://app.merge.dev/linked-accounts/accounts) and Linked Account detail pages
- General UI / UX enhancements across Dashboard
- Improvements to [duplicate Linked Account detection](https://app.merge.dev/configuration/link/configuration) and handling

# 👨‍💻

## SDK Updates

- Advanced Node [v1.1.1](https://github.com/merge-api/merge-node-client/releases/tag/v1.1.1)

December 2, 2024

https://www.merge.dev/changelog/week-1-december-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, December 2024

# 🖇️

## Integrations

[d.Vinci](https://www.merge.dev/integrations/dvinci) for ATS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/674e49c0f42d1fe71eb7b407_674e499ed943a776070b406b_d.Vinci.webp)

# ✨

## Improvements

##### **💰**    Accounting

- Enhanced edge case handling for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) with remote fields for Sage Intacct

##### 🤝    ATS

- Added support for [POST /attachments](https://docs.merge.dev/ats/attachments/) for Bullhorn
- Enhanced support for [GET /departments](https://docs.merge.dev/ats/departments/#departments_list), [GET /offices](https://docs.merge.dev/ats/offices/#offices_list) and [GET /users](https://docs.merge.dev/ats/users/#users_list) by pulling records not linked to jobs for SAP SuccessFactors
- Added mapping enhancement to “first\_name” and “last\_name” in [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Workday
- Added mapping enhancements to [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Zoho Recruit

##### **🏆**    CRM

- Added enhanced error messaging for [POST /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_create), [PATCH /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Salesforce

##### 🏠    HRIS

- Added mapping enhancement to “status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Breathe
- Added basic auth support for Payfit
- Added mapping enhancement to “employment\_type” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Paylocity
- Added support for [POST /time-off](https://docs.merge.dev/hris/time-off/#time_off_create) for SAP SuccessFactors
- Added sync performance improvements to speed up initial and subsequent syncs for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Added mapping enhancements to “manager” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added support for “request\_type” for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Paycor
- Enhanced edge case handling for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paycom
- Added support for “termination\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Planday

##### 🎟️    Ticketing

- Added support to post and edit “ticket\_type” in [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) and [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) to include all required fields for Asana
- Added support to edit “priority” and “tags” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for ClickUp
- Added pagination enhancements to Freshdesk
- Added mapping enhancement to [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Ironclad
- Added support for POST /tickets and [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Salesforce Service Cloud
- Added support to edit “creator” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) to include all required fields for ServiceNow
- Added support to post “status” in [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) and [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) to include all required fields for Trello
- Added support to post “priority” in POST and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) to include all required fields for Wrike
- Added support to post “creator”, “description”, “priority” and “status” in POST /tickets and edit “status” in [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) and enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) and [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) to include all required fields for Zendesk
- [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) ”status” query parameter now accepts arbitrary strings as parameter values, rather than just the normalized enum options
- Enhanced ticket updated webhooks to include "description" and "priority" for ClickUp
- Enhanced ticket created webhooks to include "collections", "creator", "priority", "tags" and "ticket\_url" for ClickUp
- Added support for “IN\_PROGRESS” as a "status" enum for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for ClickUp

##### 🎮     Merge Link & Dashboard

- UI enhancements to [Linked Account](https://app.merge.dev/linked-accounts/accounts) details page
- UI enhancements to [Logs](https://app.merge.dev/logs/api-requests) table and Logs side panel
- Improvements to filtering on [Logs](https://app.merge.dev/logs/api-requests) table
- UI enhancements to [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account) pages

##### 🔄     Syncing data

- Improved [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) support for [ClickUp](https://docs.merge.dev/integrations/ticketing/clickup/sync-frequencies/)
- Added support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)
- Added support for edge cases in long-running syncs for [Workday](https://docs.merge.dev/integrations/ats/workday/sync-frequencies/)
- Improved emission logic for {common\_model}.changed [webhooks](https://docs.merge.dev/basics/webhooks/merge-webhooks/)

November 20, 2024

https://www.merge.dev/changelog/week-4-november-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, November 2024

# 🗾

## Improvements to Field Mapping UX

Field Mapping is one of our most popular features, and we’ve been continuously improving its UX/UI to make it even better. Mapping fields or overriding existing ones is now more intuitive and seamless, whether at the linked account or org level.

Try it out in the Merge Dashboard!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/673e86cd468eaa6b3ec9511e_673e85eff8bfede092d1feb1_Field%2520Mapping%2520Changelog%2520Graphic.webp)

# ✨

## Improvements

##### **💰**    Accounting

- Added support for “type” selective sync filters on [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) and [GET /payments](https://docs.merge.dev/accounting/payments/#payments_list) for Netsuite, Quickbooks, Sage Intacct and Xero
- Added additional fields to “remote\_data” for [GET /contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Netsuite
- Enhanced error messaging for [POST /attachments](https://docs.merge.dev/accounting/attachments/#attachments_create) for Sage Intacct
- Enhanced error messaging for [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Xero

##### 🤝    ATS

- Added additional fields to “remote\_data” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Bullhorn
- Added support for [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for Fountain

##### 🏠    HRIS

- Added mapping enhancement to “work\_location” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added mapping enhancement to “manager” and “termination\_date” on [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SucccessFactors
- Added support for “account\_number” for [GET /bank-info](https://docs.merge.dev/hris/bank-info/#bank_info_list) for Hibob
- Added mapping enhancement to “groups” on [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Okta

##### 🎟️    Ticketing

- Added support for “snoozed” as “ON\_HOLD” enum for “status” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Kustomer
- Added support for “modified\_at” selective sync filter for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Intercom

##### 🎮     Merge Link & Dashboard

- UI enhancements for [Linked Account](https://app.merge.dev/linked-accounts/accounts) details page
- UI enhancements for [Logs](https://app.merge.dev/logs/api-requests) details page
- Updated [Settings/Notifications](https://app.merge.dev/notifications) page
- Added support for edge cases when linking [Bullhorn](https://docs.merge.dev/integrations/ats/bullhorn/sync-frequencies/) accounts

##### 🔄     Syncing data

- Efficiency optimizations for [/field-mappings](https://docs.merge.dev/hris/field-mapping/) endpoint
- Added support for edge cases in syncs for [Workday](https://docs.merge.dev/integrations/hris/workday/sync-frequencies/)

November 15, 2024

https://www.merge.dev/changelog/week-3-november-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, November 2024

# 💰

## AR/AP Selective Sync filters now available for accounting

We’ve released a new AR/AP selective sync filter, enabling you to specify only AR or AP invoices and payments. Applying these filters will optimize sync times and only pull relevant data specific for your use case.

This is in beta and available for Enterprise customers. Please reach out to your customer support manager to get access and learn more.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67378dbb27b1923e491f23c9_67378da1154578ab5564b223_Screenshot%25202024-11-14%2520at%25204.56.24%25E2%2580%25AFPM.webp)

# ✨

## Improvements

##### **💰**    Accounting

- Added support to create remote fields on [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create), [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create), [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create), [POST /purchase-orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) and [PATCH /payments](https://docs.merge.dev/accounting/payments/#payments_partial_update) for NetSuite; currently in beta
- Added support for [GET /contacts/remote-field-classes](https://docs.merge.dev/accounting/contacts/#contacts_remote_field_classes_list), [GET /journal-entries/remote-field-classes](https://docs.merge.dev/accounting/journal-entries/#journal_entries_remote_field_classes_list), [GET /payments/remote-field-classes](https://docs.merge.dev/accounting/payments/#payments_remote_field_classes_list) and [GET /purchase-orders/remote-field-classes](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_remote_field_classes_list) for NetSuite; currently in beta
- Enhanced deletion detection to account for additional transaction types for Quickbooks Desktop

##### **🤝**    ATS

- Added mapping enhancements for “Applied\_from” and “Created\_at” filters for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) in for Workday
- Added mapping enhancements for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) and [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday

##### **🏠**    HRIS

- Added mapping enhancements to “work\_location” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added mapping enhancements to “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Added mapping enhancement to “start\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Add support for [Locations](https://docs.merge.dev/hris/locations/) for SAP SuccessFactors SFTP

##### 🎮     Merge Link & Dashboard

- UI enhancements for [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) pages
- UI enhancements to [Settings](https://app.merge.dev/profile) pages
- UI enhancements for credential input screens

##### 🔄     Syncing data

- Support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)

# 👨‍💻

## SDK Updates

- Advanced Python [v1.1.3](https://github.com/merge-api/merge-python-client/releases/tag/v1.1.3)
- Advanced Node [v1.0.12](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.12)

November 7, 2024

https://www.merge.dev/changelog/week-2-november-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, November 2024

# 🖇️

## Integrations

[Onlyfy](https://www.merge.dev/integrations/onlyfy) for ATS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/672d657a8bceb6c7f8b92dac_672d655bfde42a67f695d215_Onlyfy.webp)

# **💰**

## New accounting Common Model: Employees

We’ve added a brand new Common Model to our Accounting API: [Employees](https://docs.merge.dev/accounting/employees/) is now in beta. This enables you to pull in individuals who work for the company of the linked account. This model contains both contractors and full time employees. We’ve rolled out support for Netsuite, Quickbooks, and Xero. Reach out to your customer support manager with any questions or support@merge.dev!

# ✨

## Improvements

##### 💰    Accounting

- Enhanced mapping for “status” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Netsuite
- Enhanced mapping for “email\_address” for [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Sage Intacct

##### 🤝    ATS

- Added support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Bullhorn
- Enhanced mapping for “email” for [GET /users](https://docs.merge.dev/ats/users/#users_list) for SAP Successfactor
- Updated “screening\_question\_answers” to be optional for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for UKG Pro Recruiting

##### 🏆    CRM

- Added support for “remote\_fields” for [GET /opportunities](https://docs.merge.dev/ats/applications/#applications_create) for ZohoCRM
- Added query parameter for email address to [GET /users](https://github.com/merge-api/merge-python-client/releases/tag/v1.1.3)

##### **📁    File Storage**

- Enhanced mapping and request for [POST /Folder](https://docs.merge.dev/filestorage/folders/#folders_create) for Sharepoint

##### 🏠    HRIS

- Added support for “parent\_group” for department types for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Personio
- Enhanced mapping for “employment\_type” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro

##### 🎟️    Ticketing

- Enhanced [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) to include required fields for Linear
- Added performance enhancement for sync speed for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Zendesk

##### **🎮     Merge Link & Dashboard**

- Enhancements to “Invalid credentials” [Issue](https://docs.merge.dev/hris/issues/#issues_list) type; now entitled “Account disconnected” and better guidance for remediation
- UI enhancements for integration setup screens
- Added support for edge cases when loading [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) options for SAP SuccessFactors accounts

##### 🏗️     Infrastructure

- Improved handling of [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) to improve database performance

##### 🔄     Syncing data

- Enhancements to sync schedule generation for [Linked Accounts](https://docs.merge.dev/get-started/linked-account/) with customer sync plans
- Added support for edge cases in syncs for [Justworks](https://docs.merge.dev/integrations/hris/justworks/)

# 👨‍💻

## SDK Updates

- [Advanced Python v1.1.3](https://github.com/merge-api/merge-python-client/releases/tag/v1.1.3)

October 31, 2024

https://www.merge.dev/changelog/week-1-november-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, November 2024

# 🖇️

## Integrations

[Manatal](https://www.merge.dev/integrations/manatal) for ATS is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/67241bb2dcffb5b68ac2d1e8_67241b894722e9ffb193fb9e_Manatal.webp)

# **💰**

## Remote Field Support for key accounting integrations!

Remote Fields is now supported for NetSuite and Sage Intacct across key Common Models, including Journal Entry, Invoice, Payment, Contact, and more.

You’ll now be able to:

- Pull metadata and values on all remote fields for an object, including the fields data type, if the field is required, and if the field is custom
- POST back objects to your customers’ ERP with any field

We’ll continue to roll out additional capabilities and integration support. This feature is currently in beta. If you’re interested in getting access, reach out to your CSM.

# ✨

## Improvements

##### 💰    Accounting

- Added support to create remote fields on [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create), [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create), [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) and [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create) for Sage Intacct; currently in beta
- Added support to create remote fields on [GET /contacts/remote-field-classes](https://docs.merge.dev/accounting/contacts/#contacts_remote_field_classes_list), [GET /invoices/remote-field-classes](https://docs.merge.dev/accounting/invoices/#invoices_remote_field_classes_list), [GET /journal-entries/remote-field-classes](https://docs.merge.dev/accounting/journal-entries/#journal_entries_remote_field_classes_list) and [GET /payments/remote-field-classes](https://docs.merge.dev/accounting/payments/#payments_remote_field_classes_list) for Sage Intacct; currently in beta
- Added support to create remote fields on [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create), [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) and [PATCH /invoices](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) for NetSuite; currently in beta
- Added support for [GET /expenses/remote-field-classes](https://docs.merge.dev/accounting/expenses/#expenses_remote_field_classes_list) and [GET /invoices/remote-field-classes](https://docs.merge.dev/accounting/invoices/#invoices_remote_field_classes_list) for NetSuite; currently in beta
- Added support for “account” for line\_items when invoice.type = accounts\_receivable for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Zoho Books
- Enhanced mapping for “status” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Xero

##### 🤝    ATS

- Added support for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Occupop
- Enhanced“phone number creation for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday
- Enhanced error handling for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for JazzHR
- Enhanced pagination for [GET /users](https://docs.merge.dev/ats/users/#users_list) for SAP Successfactors

##### 🏠    HRIS

- Enhanced [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) to include when an employee’s “work\_email” is removed for ADP Workforce Now
- Added support for “manager” and enhanced “remote\_data” to include additional fields for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Entra ID
- Added support for organizations, departments, and division group types for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Okta
- Added support for “manager” and “cost\_center” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Okta

##### 🎟️    Ticketing

- Enhanced “status” [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ClickUp
- Enhanced ticket changed webhook to reflect “name” changes for ClickUp
- Enhanced pagination for Freshdesk
- Added performance enhancements to all models Teamwork

##### 🔗     Linked accounts

- Improved logic for flagging linked accounts as [relink needed](https://help.merge.dev/en/articles/6461253-what-does-relink-needed-mean)
- Added support for edge cases when relinking Workday [SFTP](https://help.merge.dev/en/articles/9054729-secure-file-transfer-protocol-sftp) accounts

##### 🔄     Syncing data

- Improved performance for long-running syncs for [Quickbooks Online](https://docs.merge.dev/integrations/accounting/quickbooks-online/sync-frequencies/)
- Added support for edge cases when configuring [Scopes via API](https://docs.merge.dev/filestorage/scopes/#:~:text=Merge%20Docs&text=Scopes%20allows%20for%20precise%20controlall%20of%20its%20associated%20fields.)
- Added query parameters for name and email address to [GET /contacts](https://docs.merge.dev/accounting/contacts/#contacts_list)

October 24, 2024

https://www.merge.dev/changelog/week-4-october-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, October 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhanced sync efficiency for large Xero accounts
- Released [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) support for Sage Intacct

##### 🤝    ATS

- Enhanced support and reliability for Workday [POST /Attachments](https://docs.merge.dev/ats/attachments/#attachments_create)
- Enhanced Bullhorn support for [Job Interview Stages](https://docs.merge.dev/ats/job-interview-stages/)
- Support for [screening questions](https://docs.merge.dev/ats/screening-questions/) for TeamTailor

##### 🏆    CRM

- Enhanced Salesforce [PATCH /Accounts](https://docs.merge.dev/crm/accounts/#accounts_partial_update)

##### 🏠    HRIS

- Enhanced reliability for UKG Pro Employments with different permission sets
- Enhanced support for Deel API v2 migration
- Enhanced linking support for Dayforce Developer environments

##### 🎟️    Ticketing

- Enhanced support for Zendesk [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve)
- Enhanced sync filters for Zendesk and Linear

##### **📁**    File Storage

- Enhanced Sharepoint webhooks
- Enhanced Partnership linking flow for Box

##### 🎮    Merge Link and Dashboard

- Enhancements to UX for configuring [Scopes via Dashboard](https://app.merge.dev/common-models/hris)
- Enhancements to UX for [configuring integration settings](https://app.merge.dev/integrations/hris) in Dashboard
- Enhancements to UI for Issue details page in Dashboard

##### 🏗️    Infrastructure

- Enhancements to remove key bottlenecks on database performance

##### 🔄    Syncing Data

- Added support for edge cases in [OAuth](https://help.merge.dev/en/articles/9891389-workday-how-do-i-link-using-oauth) for [Workday](https://docs.merge.dev/integrations/hris/workday/sync-frequencies/)
- Added support for edge cases in syncs for [Justworks](https://docs.merge.dev/integrations/hris/justworks/sync-frequencies/)
- Added support for edge cases when configuring [Scopes via API](https://docs.merge.dev/hris/scopes/)

October 17, 2024

https://www.merge.dev/changelog/week-3-october-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, October 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhanced mapping for [Account](https://docs.merge.dev/accounting/accounts/) by now including account\_number for Zoho Books

##### **🤝**    ATS

- Enhanced webhooks to delineate ”deletion” and “changed” events for Linear
- Enhanced reliability of the [POST /application](https://docs.merge.dev/ats/applications/#applications_create) endpoint to cover more nested object support for Workday

##### 🏆    CRM

- Added remote field support for [Opportunities](https://docs.merge.dev/crm/opportunities/) for ZohoCRM

##### 🏠    HRIS

- Enhanced error handling and reliability for UKG Pro custom fields when credentials no longer have access to the field
- Expand query param added to [GET /timesheet-entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list)

##### 📁    File Storage

- Enhanced integration efficiency when Group.users scope is disabled
- Improved the linking experience for OneDrive with partner credentials

##### 📞     API

- Enhancements to error logic for [Scopes via API](https://docs.merge.dev/filestorage/scopes/)

##### 🔄     Syncing Data

- Added support for edge cases in syncs for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/)
- Enhancements to [sync scheduling](https://docs.merge.dev/basics/sync-frequency/) logic

# 👨‍💻

## SDK Updates

- [Advanced Python v1.1.2](https://github.com/merge-api/merge-python-client/releases/tag/v1.1.2)
- [Advanced Java v1.0.17](https://github.com/merge-api/merge-java-client/releases/tag/v1.0.17)

October 10, 2024

https://www.merge.dev/changelog/week-2-october-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, October 2024

# 🔐

## SFTP observability and error handling

We now surface SFTP-specific errors directly in our dashboard (under [Issues](https://app.merge.dev/issues?status=ONGOING&utm_source=hs_email&utm_medium=email&_hsenc=p2ANqtz--evBVwbVGnuFOwF7ABYcY_UIONHH2qiULHGIY5BTl3uwzQyG2YIFJ0y9MoJEkiXUssf4Fw)). This provides you guidance on what the exact issue is when an SFTP does not successfully upload, making it easier to troubleshoot. The 4 types of errors that are surfaced are:

- Wrong file type
- Wrong file name
- Missing required fields
- Incorrectly formatted rows

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6708093b6d0f6f8bc5a5a267_670809366232f34146310d63_Screenshot%25202024-10-08%2520at%25201.54.51%25E2%2580%25AFPM.webp)

You can learn more about SFTP [here](https://help.merge.dev/en/articles/9054729-secure-file-transfer-protocol-sftp).

# ✨

## Improvements

##### 💰    Accounting

- Enhanced pagination for [GET /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Sage Intacct

##### **🤝**    ATS

- Enhanced “remote\_data” to include more job qualification details for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Workday

##### 🏠    HRIS

- Added pagination and performance enhancements [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for CyberArk
- Enhanced mapping for “parent\_group” when a parent group is updated for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Lucca
- Added support for rate limits for Paycom
- Enhanced mapping for “manager” when a manager is updated for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro
- Enhanced error messaging for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro

##### 🎟️    Ticketing

- Enhanced mapping for “assignee” for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Linear
- Enhanced mapping for [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Zendesk

##### 🎮    Merge Link and Dashboard

- UI improvements for [Settings/Profile](https://app.merge.dev/profile) page
- UI improvements for right panel on [Linked Account](https://docs.merge.dev/get-started/linked-account/) overview page
- Added support for edge cases in [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) configuration when [Redact Unmapped Data](https://help.merge.dev/en/articles/8358419-redacting-unmapped-data) is enabled
- Improvements to “Administrator role required” flows
- UI updates for [detailed error messages](https://help.merge.dev/en/articles/7131146-detailed-error-messaging) screen
- General UI updates

##### 🔄     Syncing Data

- Added support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)
- Added support for edge cases in [Passthrough Requests](https://docs.merge.dev/supplemental-data/passthrough/overview/) when they contain XML

# 👨‍💻

## SDK Updates

- [Advanced Java (Kotlin/JVM) v1.0.16](https://github.com/merge-api/merge-java-client/)
- [Advanced Node v1.0.11](https://github.com/merge-api/merge-node-client/)

October 3, 2024

https://www.merge.dev/changelog/week-1-october-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, October 2024

# 🖇️

## Integrations

[ADP Run](https://www.merge.dev/integrations/adp-run) (HRIS), [Easycruit](https://www.merge.dev/integrations/easycruit) (ATS), [Gem](https://www.merge.dev/integrations/gem) (ATS), and [Welcome to the Jungle](https://www.merge.dev/integrations/welcome-to-the-jungle) (ATS) are now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66feeb0873a09b88e79d00e9_66feeade10b9b29f277fb647_Week%2520of%2520Oct%25202%2520changelog.webp)

# ✨

## Improvements

##### 💰    Accounting

- Added support for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list), [POST /accounts](https://docs.merge.dev/accounting/accounts/#accounts_create), [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) and [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Clearbooks
- Added support [GET /company-info](https://docs.merge.dev/accounting/company-info/#company_info_list), [GET /tracking-categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list), [GET /income-statements](https://docs.merge.dev/accounting/income-statements/#income_statements_list), [GET /balance-sheets](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list), [GET /cash-flow-statements](https://docs.merge.dev/accounting/cash-flow-statements/#cash_flow_statements_list), [PATCH /invoices](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) and [PATCH /payments](https://docs.merge.dev/accounting/payments/#payments_partial_update) for Freshbooks
- Added support for additional fields for “OPEN” enum value for [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Freshbooks
- Added support for "inclusive\_of\_tax" and "tax\_rate" for line items for [GET /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create), [GET /expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create), [GET /credit-notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) and [GET /vendor-credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Sage Intacct
- Enhanced pagination for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct
- Enhanced error messaging for non-editable fields for [PATCH /invoices/{id}](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) for Quickbooks Online

##### **🤝**    ATS

- Enhanced mapping for “interviewer” when the interviewer is updated for [GET /interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Ashby
- Enhanced mapping for “first\_name” and “last\_name” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create)
- Added support for additional mapping cases for “first\_name” for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Lever
- Added performance enhancements if attachment scope is disabled to [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Workday

##### **🏆**    CRM

- Added support for additional edge cases to avoid duplicate custom fields in [PATCH /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Salesforce

##### **🏠**    HRIS

- Added performance enhancements for initial syncs for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for BambooHR
- Updated Deel from V1 to V2 endpoints
- Enhanced mapping for “gender” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Enhanced “balance” to handle nulls for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Workday

##### **🎟️**    Ticketing

- Support for modified\_after selective sync filter on [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana and Freshdesk
- Enhanced timestamps to ensure all ticket changes are captured for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Azure DevOps
- Enhanced pagination for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Linear

##### 🎮     Merge Link

- For [Comeet](https://docs.merge.dev/integrations/ats/comeet/sync-frequencies/) customers with partnerships, applicable Comeet [linking flow steps](https://docs.merge.dev/get-started/link/) now dynamically populate with the customer name
- Added support for edge cases when linking [BambooHR](https://docs.merge.dev/integrations/hris/bamboohr/sync-frequencies/) [Linked Accounts](https://docs.merge.dev/get-started/linked-account/)

##### 🔄    Syncing Data

- Added support for XML character edge cases in [SOAP APIs](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through)
- Added support for edge cases in syncs for [SharePoint](https://docs.merge.dev/integrations/filestorage/sharepoint/sync-frequencies/)

September 26, 2024

https://www.merge.dev/changelog/week-4-september-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, September 2024

# 🐚

## Shell data filtering

Merge now automatically detects and hides newly created shell data records, ensuring incomplete data doesn’t appear anymore.

Shell data records are objects where most fields are null except metadata (e.g., IDs and timestamps). Shell data can be temporarily created due to the ordering of model syncs.

If you do need shell data records, be sure to include the query parameter `include_shell_data=True` when requesting data.

Shell object references will still be returned on any related non-shell objects, even without including the `include_shell_data=true parameter` (e.g., the UUID for a shell Location object will still display on a corresponding non-shell Employee object).

You can learn more [here](https://help.merge.dev/en/articles/9713879-what-is-shell-data-filtering)! If you have any further questions, please reach out to your CSM or [support@merge.dev](mailto:support@merge.dev).

# ✨

## Improvements

##### 💰    Accounting

- Support for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Quickbooks Online

##### **🤝**    ATS

- Support for [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Bullhorn
- Enhancements to [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Greenhouse
- Support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for SAP SuccessFactors

##### **🏠**    HRIS

- Support for “work\_location” for terminated employees for ADP Workforce Now SFTP
- Enhancements to “managers” for [Employees](https://docs.merge.dev/hris/employees/) for ADP Workforce Now SFTP
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Enhancements to “home\_location” and “work\_location” for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for Workday

##### **📁**    File Storage

- Enhanced [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_download_retrieve) for Sharepoint

##### 🎮    Merge Link

- For [Comeet](https://docs.merge.dev/integrations/ats/comeet/sync-frequencies/) customers with partnerships, applicable Comeet [linking flow steps](https://docs.merge.dev/get-started/link/) now dynamically populate with the customer name
- Support for edge cases when linking [BambooHR](https://docs.merge.dev/integrations/hris/bamboohr/sync-frequencies/) [Linked Accounts](https://docs.merge.dev/get-started/linked-account/)

##### 🔄    Syncing Data

- Support for XML character edge cases in [SOAP APIs](https://www.merge.dev/blog/building-a-soap-api-integration-when-you-already-know-rest-the-full-walk-through)
- Support for edge cases in syncs for [SharePoint](https://docs.merge.dev/integrations/filestorage/sharepoint/sync-frequencies/)

‍

September 19, 2024

https://www.merge.dev/changelog/week-3-september-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, September 2024

# ✨

## Improvements

##### 💰    Accounting

- Support for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list), [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create), [GET /expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create), [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create), [GET /items](https://docs.merge.dev/accounting/items/#items_list), [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create), [GET /tax rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) and [GET /transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Freshbooks
- Enhancements to pagination for Sage Intacct
- Added performance enhancements to for [GET /payments](https://docs.merge.dev/accounting/payments/#payments_list) for Zoho Books
- Support for [GET /tax-rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Zoho Books

##### **🤝**    ATS

- Support for “status” for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Avature
- Support for “job\_posting\_urls” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Avature
- Support for “status” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Bullhorn
- Enhancements to pagination for Tellent
- Enhancements to [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) (with screening questions) for Workday

##### 🏠    HRIS

- Support for [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) and [GET /payroll-runs](https://docs.merge.dev/hris/payroll-runs/#payroll_runs_list) for Gusto
- Enhancements to “balance” for [GET /time-off-balances](https://docs.merge.dev/hris/time-off/#time_off_list) for Workday

##### 🎮    Merge Link

- Enhancements to data permissions screen in [Merge Link](https://docs.merge.dev/get-started/link/)
- Enhancements to logic for determining missing permissions [issues](https://help.merge.dev/en/articles/5389726-issue-tracking)
- Enhancements to admin needed flow in Merge Link

##### 🔄    Syncing Data

- Support for edge cases when syncing [Advanced Field Mappings](https://help.merge.dev/en/articles/9269164-advanced-field-mapping-with-jmespath)
- Support for edge cases in syncs for [Sage Intacct](https://docs.merge.dev/integrations/accounting/sage-intacct/sync-frequencies/)
- Support for edge cases in syncs for [ADP](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/)

‍

September 12, 2024

https://www.merge.dev/changelog/week-2-september-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, September 2024

# ✨

## Improvements

##### 💰    Accounting

- Support for custom fields for [GET /contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) and [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Netsuite
- Support for “transaction\_date” for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Netsuite
- Added performance enhancements for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct

##### 🤝    ATS

- Enhancements to “first\_name” and “last\_name” for [GET /users](https://docs.merge.dev/ats/users/#users_list) for iCIMS
- Added performance enhancements to [GET /interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Greenhouse
- Added performance enhancements to [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Tellent
- Support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for UKG Pro Recruiting
- Support to link with ukg.net domains for UKG Pro Recruiting
- Enhancements to pagination for [Tellent](https://docs.merge.dev/integrations/ats/tellent/sync-frequencies/)
- Enhancements to pagination for [Greenhouse](https://docs.merge.dev/integrations/ats/greenhouse/sync-frequencies/)

##### 🏠    HRIS

- Enhancements to [GET /time-off/meta/post](https://docs.merge.dev/hris/time-off/#time_off_meta_post_retrieve) for BambooHR
- Enhancements to [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Dayforce
- Support for “state” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Entra
- Support for edge cases in [Justworks](https://docs.merge.dev/integrations/hris/justworks/sync-frequencies/) syncs

##### 🎟️    Ticketing

- Support for modified\_after selective sync filter on [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Enhancements to [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) for [Trello](https://docs.merge.dev/integrations/ticketing/trello/sync-frequencies/)

September 4, 2024

https://www.merge.dev/changelog/week-1-september-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, September 2024

# 🔐

## SFTP is now available!

Give your customers the option to securely transfer files and CSV reports between third-party platforms and Merge.

- Your customers receive step-by-step guidance on how to automate reports to a secure Merge-hosted SFTP server in Merge Link
- Scheduled reports are fully normalized to our Common Models, ensuring all functionality for Merge integrations apply to any SFTP integrations
- SFTP is currently available for select HRIS and ATS integrations

Learn more about how Merge SFTP can help your customers sync data via files automatically or manually [here](https://www.merge.dev/blog/merge-sftp).

Note: if you’re interested in this feature, please reach out to your CSM to get access as it is in beta for professional and enterprise customers.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66d8db2897259be9218ec119_66d8dae534448a7ec8dda8aa_CSV%2520%253A%2520SFTP.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for [GET /tax-rate](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Freshbooks
- Added new fields "code" "name" "status" and "country" and new sub-model "tax\_components" to [GET /tax-rate](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Sage Intacct
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items to [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) & [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Added “project\_id” as an integration parameter for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Sage Intacct

##### 🤝    ATS

- Enhancements to “name” and “remote\_id” for [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Bullhorn
- Enhancements to “recruiters” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Lever
- Enhancements to error messaging for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Lever
- Enhancements to enums for “status” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Enhancements to “created\_at” selective sync filter for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Workday

##### 🏠    HRIS

- Support for employments for inactive employees for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Enhancements to “remote\_data” for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for Paylocity
- Enhancements to linking for EU accounts for Teamwork
- Added OAuth support for Workday
- Enhancements to “work\_location” and “home\_locations” for [GET /employees](https://docs.merge.dev/hris/employees/) for Workday

##### 🎟️    Ticketing

- Enhancements to [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Salesforce Service Cloud
- Enhancements to “modified\_after” selective sync filter for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Trello

August 28, 2024

https://www.merge.dev/changelog/week-5-august-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, August 2024

# 🖇️

## Integrations

[Taleez](https://merge.dev/integrations/taleez) for ATS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66cf59d1f3f459ae74461e31_66cf59c1e2e29f5536c680c6_Taleez.webp)

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “tracking\_categories” for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Quickbooks Online

##### 🤝    ATS

- Support to create nested new candidates for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Ashby, BambooHR, Bullhorn, Comeet, Greenhouse, JazzHR, Jobadder, Jobvite, SAP SuccessFactors, SmartRecruiters, Teamtailor, UKG Pro Recruiting, Workable, Workday
- Enhancements to “status” and “type” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Oracle Fusion Recruiting Cloud
- Support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Workday
- Enhancements to sync performance for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Workday

##### 🏆    CRM

- Enhancements to “account” for [GET /contacts](https://docs.merge.dev/crm/contacts/#contacts_list) for Hubspot
- Enhancements to “stage” for [PATCH /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update)

##### 🏠    HRIS

- Enhancements to “manager” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Enhancements to “remote\_id” for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Hibob
- Enhancements to “status” for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Hibob
- Enhancements to [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Hibob
- Enhancements to [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for for Paylocity
- Enhancements to “start\_time” and “end\_time” for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Personio
- Support for “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Remote
- Enhancements to linking for Zelt

August 21, 2024

https://www.merge.dev/changelog/week-4-august-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, August 2024

# 🖇️

## Integrations

[Traffit](https://www.merge.dev/integrations/traffit) for ATS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66c67a26baa1401ea4fca948_66c679eb9c67cfc6abb0e56d_Traffit.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for [Contact](https://docs.merge.dev/accounting/contacts/) created, updated, and deleted webhooks for Xero
- Enhancements to “description” for [GET /tax-rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Xero
- Enhancements to [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Xero

##### 🤝    ATS

- Enhancements to “remote\_data” for [GET /interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Ashby
- Enhancements to “hiring\_managers” and “recruiters” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Ashby
- Enhancements to error messaging for [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for Ashby
- Support for “source” on nested applications for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workable
- Enhancements to “description” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Workday
- Enhancements to “candidates” on [GET /activities](https://docs.merge.dev/ats/activities/#activities_list) for SAP SuccessFactors
- Enhancements to [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for SmartRecruiters

##### 🏆    CRM

- Enhancements to error messaging for [POST /engagements](https://docs.merge.dev/crm/engagements/#engagements_create) for Salesforce

##### 🏠    HRIS

- Enhancements to “work\_location” for [Employees](https://docs.merge.dev/hris/employees/) for ADP SFTP
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian Dayforce
- Support for “managers” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Google Workspace
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Google Workspace
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Hibob
- Support for “ethnicity” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Oracle HCM
- Support for “parent\_group” for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Personio
- Support for “type” for departments for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for UKG Pro

##### **🎟️**    Ticketing

- Added new “remote\_data\_path” and enhanced “remote\_data” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira

##### 🎮    Merge Link and Dashboard

- UI improvements for configuring [Field Mappings](https://docs.merge.dev/supplemental-data/field-mappings/overview/) in Dashboard
- UI/UX improvements to [Billing](https://app.merge.dev/billing) page in Dashboard
- General UI improvements in Dashboard
- Broad improvements to [Merge Link](https://docs.merge.dev/get-started/link/) loading speed
- Added support for edge cases when authenticating [Paylocity](https://docs.merge.dev/integrations/hris/paylocity/) [Linked Accounts](https://docs.merge.dev/get-started/linked-account/)
- UX improvements for [File Picker](https://docs.merge.dev/filestorage/file-picker/)
- General UI improvements in Merge Link

##### 📄    Documentation

- Improved filtering on [Use Cases](https://docs.merge.dev/use-cases/) page

##### 🔄    Syncing Data

- Improvements to [Common Model synced webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/) emission logic
- Improved rate limit management logic for [Paycor](https://docs.merge.dev/integrations/hris/paycor/)
- Added support for edge cases in syncs for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/)

August 8, 2024

https://www.merge.dev/changelog/week-2-august-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, August 2024

# 🖇️

## Integrations

[Darwinbox](https://www.merge.dev/integrations/darwinbox) for HRIS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66b40dbd8153226c9880fd30_66b40d9578b25adf13b4da82_Darwinbox%2520integration%2520Changelog.webp)

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “remote\_data” for [GET /accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Netsuite

##### 🤝    ATS

- Enhancements to “source” for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for UKG Pro Recruiting
- Enhancements to error messaging for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for UKG Pro Recruiting
- Enhancements to [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) and [GET /reject-reasons](https://docs.merge.dev/ats/reject-reasons/#reject_reasons_list) for Workday
- Enhancements to [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Workday

##### 🏆    CRM

- Added performance enhancements to [GET /engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Hubspot

##### 🏠    HRIS

- Enhancements to “type” for [POST /time-off](https://docs.merge.dev/hris/time-off/#time_off_create) for BambooHR
- Support for “parent\_group” for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for Lucca
- Enhancements to [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Personio
- Enhancements to “manager” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro
- Enhancements to “remote\_data” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Workday
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### **🎟️**    Ticketing

- Enhancements to linking flow for Hubspot Ticketing

##### 🎮    Merge Link and Dashboard

- UX improvements for configuring [Scopes](https://docs.merge.dev/filestorage/scopes/) in Dashboard
- General UI improvements in Dashboard
- UX improvements for successful linking flows in [Merge Link](https://docs.merge.dev/get-started/link/)
- UX improvements for already integrated flow in Merge Link
- General UI improvements in Merge Link

##### 🔄     Syncing Data

- Support for edge cases in syncs for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/)

August 1, 2024

https://www.merge.dev/changelog/week-1-august-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, August 2024

# 🪄

## White-label Guides

Automatically white-label all Merge help guides with the click of a button, creating a seamless experience for your customers.

Go to the Merge Dashboard settings, upload your logo, and pick a subdomain. All links in Merge Link will magically redirect to your selected subdomain, removing all references to Merge. This feature is available on our Enterprise plan.

Note if you have any overridden guide links they will still take priority and work as expected.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abb99d2546752d56cb80d6_66abb9465797179973043336_White%2520label%2520guides.webp)

# 🗣️

## Merge Link Localization

Merge Link is now available in German. Your customers can now connect to any of Merge’s 200+ integrations in their native language.

[Learn more](https://help.merge.dev/en/articles/9612167-merge-link-localization) on how to automatically translate your product integrations’ auth flow for international customers. This feature is available on our Enterprise Plan.

We will be supporting more languages in the near future. If you are an Enterprise customer and have any requests, please let your Customer Support Manager know.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abb99c2546752d56cb80ce_66abb969e67bac6644d9c84e_Merge%2520Link%2520localization%2520pic.webp)

‍

# 🖇️

## Integrations

[Sage People](https://www.merge.dev/integrations/sage-people) for HRIS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66abb99d2546752d56cb80d2_66abb9747679f189b6786208_Sage%2520People.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for [Contact](https://docs.merge.dev/accounting/contacts/) created, updated, and deleted webhooks for Quickbooks Online

##### 🤝    ATS

- Enhancements to “stage\_order” for [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Enhancements to [Candidate](https://docs.merge.dev/ats/candidates/) created webhooks for Greenhouse
- Support for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Jobvite
- Enhancements to “hiring\_managers” and “recruiters” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Jobvite
- Enhancements to “title” for [GET /job-postings](https://docs.merge.dev/ats/job-postings/#job_postings_list) for SAP SuccessFactors
- Support for “rejected\_at” for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Tellent
- Enhancements to “phone\_number” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday

##### 🏆    CRM

- Enhancements to [POST /engagements](https://docs.merge.dev/crm/engagements/#engagements_create) for Salesforce

##### 🏠    HRIS

- Enhancements to [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for BambooHR
- Enhancements to “manager” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paylocity
- Support for updated managers in [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Ready
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Ready
- Enhancements to “job\_title” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Ready

##### 📁    File Storage

- Enhancements to missing permissions error messaging for Dropbox, OneDrive and Sharepoint
- Enhancements to [GET /files](https://docs.merge.dev/filestorage/files/#files_list) and [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Google Drive

##### 🎮    Merge Link and Dashboard

- Support for edge cases in URL validation in [Merge Link](https://docs.merge.dev/get-started/link/)
- General UI improvements in Merge Link

##### 🔄    Syncing Data

- Support for edge cases in syncs for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/)
- Support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/)
- Support for edge cases in sync for [Intercom](https://docs.merge.dev/integrations/ticketing/intercom/)

# 👨‍💻

## SDK Updates

- [Node SDK v1.0.9](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.9)
- [Java SDK v1.0.15](https://github.com/merge-api/merge-java-client/releases/tag/v1.0.15)
- [Python SDK v1.0.13](https://github.com/merge-api/merge-python-client/releases/tag/v1.0.13)
- [Go SDK v1.0.9](https://github.com/merge-api/merge-go-client/releases/tag/v1.0.9)
- [Ruby SDK v.0.1.4](https://github.com/merge-api/merge-ruby-client/releases/tag/v0.1.4)
- [C# SDK v0.1.0](https://github.com/merge-api/merge-csharp-client/releases/tag/0.1.0)

July 25, 2024

https://www.merge.dev/changelog/week-4-july-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, July 2024

# ✨

## Improvements

##### 💰    Accounting

- Support for [purchase](https://docs.merge.dev/accounting/purchase-orders/) and [vendor credit](https://docs.merge.dev/accounting/vendor-credits/) created, updated, and deleted webhooks for Quickbooks Online
- Support for vendor addresses for [GET /addresses](https://docs.merge.dev/accounting/addresses/#addresses_retrieve) for Sage Intacct

##### **🤝**    ATS

- Support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for BambooHR
- Enhancements to “file\_url” for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for SmartRecruiters

##### **🏆**    CRM

- Added sync enhancements to [GET /accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for Salesforce

##### **🏠**    HRIS

- Enhancements to “remote\_data” for [Employees](https://docs.merge.dev/hris/employees/) for ADP SFTP
- Enhancements to “balance” for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for ADP
- Enhancements to “remote\_data” for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for BambooHR
- Enhancements to [GET /employments](https://docs.merge.dev/hris/employees/#employees_list) for Deel
- Support for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Hibob
- Enhancements to [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Humaans
- Enhancements to “balance” for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Humaans
- Enhancements to “mobile\_phone\_number” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paychex
- Enhancements to “balance” for [GET /time-off-balances](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for Personio and SageHR
- Added performance enhancements for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Ready

##### **🎟️**    Ticketing

- Support for PDFs for [POST /attachments](https://docs.merge.dev/ticketing/attachments/#attachments_create) for Zendesk

##### 🎮    Merge Link and Dashboard

- UX improvements for when a [Linked Account](https://docs.merge.dev/get-started/linked-account/) is put into [Relink Needed](https://help.merge.dev/en/articles/6461253-relink-needed-status)
- General Dashboard UI updates
- Improvements to Admin Needed screen in [Merge Link](https://docs.merge.dev/get-started/link/)
- General Merge Link UI updates

##### 🔄     Syncing Data

- Support for edge cases when overriding common models for [SAP SuccessFactors](https://docs.merge.dev/integrations/hris/sap-successfactors/sync-frequencies/)
- Support for edge cases in [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/) syncs
- Improvements to [Deleted Data Detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection) for large Linked Accounts
- Improvements to calculation of is\_initial\_sync field on [/sync-status](https://docs.merge.dev/hris/sync-status/) endpoint

July 18, 2024

https://www.merge.dev/changelog/week-3-july-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, July 2024

# ✨

## Improvements

##### 💰    Accounting

- Added new fields "code" "name" "status" and "country" and new sub-model "tax\_components" to [GET /tax-rates](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for NetSuite, Quickbooks Online, and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items to [GET /transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for NetSuite and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for NetSuite and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for NetSuite and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create) for NetSuite and Xero
- Added new fields for "inclusive\_of\_tax" and "tax\_rate" for line items for [POST /purchase-order](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for NetSuite and Xero
- Enhancements to “total\_amount” for [GET /expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Sage Intacct

##### 🤝    ATS

- Support for “job\_posting\_url” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Smartrecruiters
- Enhancements to “source” for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Smartrecruiters
- Enhancements to Workable OAuth

##### 🏠    HRIS

- Support for custom reports for ADP SFTP
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Added pagination enhancements for Oracle HCM
- Support for divisions for [GET /groups](https://docs.merge.dev/hris/groups/#groups_list) for SAP SuccessFactors
- Added sync enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Enhancements to [GET](https://docs.merge.dev/hris/time-off/#time_off_list) and [POST /time-off](https://docs.merge.dev/hris/time-off/#time_off_create) for Workday

##### 🎟️    Ticketing

- Support for [POST /attachments](https://docs.merge.dev/ticketing/attachments/#attachments_create) for Wrike
- Enhancements to “priority” for [PATCH /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Zendesk

##### 🎮     Merge Link and Dashboard

- UX improvements to partner credentials configuration in [Dashboard](https://app.merge.dev/)
- Improved loading speed for [Linked Account](https://docs.merge.dev/get-started/linked-account/) overview page
- Improved error messaging when validation of a 3rd party platform URL fails in [Merge Link](https://docs.merge.dev/get-started/link/)
- General UI improvements to Merge Link screens

##### 🔄     Syncing Data

- Support for edge cases in response body formatting for [Sage Intacct](https://docs.merge.dev/integrations/accounting/sage-intacct/sync-frequencies/)
- Efficiency improvements for [Jobvite](https://docs.merge.dev/integrations/ats/jobvite/sync-frequencies/) syncs
- Improved logic for calculating [Relink Needed](https://help.merge.dev/en/articles/6461253-relink-needed-status) for [Justworks](https://docs.merge.dev/integrations/hris/justworks/sync-frequencies/) Linked Accounts
- Improved logic for calculating Relink Needed for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/) Linked Accounts
- Support for edge cases when authenticating with ADP Workforce Now
- Support for edge cases when processing files returned by 3rd party platform
- General improvements to sync speeds across integrations

July 11, 2024

https://www.merge.dev/changelog/week-2-july-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, July 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to line item “quantity” and “unit\_price” [POST /invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Support for “sage\_customer\_or\_vendor\_id” as an integration parameter for [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Sage Intacct
- Updated Xero integration to comply with Xero's new record limits

##### 🤝    ATS

- Enhancements to error messaging for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for BambooHR
- Enhancements to “remote\_data” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Bullhorn
- Enhancements to error messaging for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for SmartRecruiters
- Enhancements to “source” for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for SAP SuccessFactors
- Enhancements to “file\_name” for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Workable
- Support for “attachments” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday

##### 📁    File Storage

- Enhancements to “remote\_data” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for Sharepoint

##### 🏠    HRIS

- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for 7Shifts
- Enhancements to “avatar” [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BreatheHR
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Officient
- Enhancements to “groups” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Personio

##### 🎮     Merge Link and Dashboard

- UI improvements to pages in [Merge Link](https://docs.merge.dev/get-started/link/)
- UX improvements for [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) filter configuration in Dashboard

##### 🔄     Syncing Data

- Support for edge cases in [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/) syncs
- Support for edge cases in basic auth password formatting
- Improved logic [Linked Account](https://docs.merge.dev/get-started/linked-account/) synced [webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/) for initial syncs
- Enhancements to “candidate” for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create) for Greenhouse
- Enhancements to “recruiters” on [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Oracle Taleo

July 3, 2024

https://www.merge.dev/changelog/week-1-july-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, July 2024

# ✨

## Improvements

##### 💰    Accounting

- Support for [invoice](https://docs.merge.dev/accounting/invoices/), [payment](https://docs.merge.dev/accounting/payments/), [journal entry](https://docs.merge.dev/accounting/journal-entries/), [purchase order](https://docs.merge.dev/accounting/purchase-orders/), and [credit note](https://docs.merge.dev/accounting/credit-notes/) created, updated, and deleted webhooks for Quickbooks Online
- Support for [invoice](https://docs.merge.dev/accounting/invoices/) created, updated, and deleted webhooks for Xero
- Support for partner authentication for FreeAgent and Wave Financial

##### **🤝**     ATS

- Enhancements to [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Support for basic auth for iCIMS
- Updated Jobvite to comply with new header requirements
- Support for partner authentication for JobAdder, Lano, and Zoho Recruit

##### 🏆     CRM

- Improved sync performance for emails and calls for [GET /engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Hubspot
- Support for partner authentication for Accelo, Keap, Microsoft Dynamics 365 Sales, and Teamleader

##### 🏠     HRIS

- Enhancements to remote data for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for 7Shifts
- Enhancements to “start\_date” for [employees](https://docs.merge.dev/hris/employees/) for ADP SFTP
- Enhancements to “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Factorial
- Improved sync performance for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Hibob
- Support for partner authentication for Cezanne HR, Employment Hero, Factorial, Google Workspace, Officient, PayCaptain, Paycor, Square Payroll, and Zoho People

##### 🎟️     Ticketing

- Added Oauth support for Ironclad
- Enhancements to [GET /users](https://docs.merge.dev/ticketing/users/#users_list) for Zendesk
- Support for partner authentication for Gitlab, Help Scout, Ironclad, Linear, Salesforce Service Cloud, Wrike, Zendesk, Zoho BugTracker, and Zoho Desk

##### 🎮      Merge Link and Dashboard

- Revamped model for configuring partner credentials in [Dashboard](https://app.merge.dev/login)
- UI improvements for selective sync configuration pages in [Merge Link](https://docs.merge.dev/get-started/link/)
- UI improvements for custom fields configuration pages in Merge Link
- UI improvements for mapping additional fields pages in Merge Link
- General UI improvements across linking flows in Merge Link

##### 🔄      Syncing Data

- Improvements for [Deleted Data Detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection)
- Added support for edge cases in sync scheduling across integrations

# 👨‍💻

## SDK Updates

- Advanced Python SDK [v1.0.12](https://github.com/merge-api/merge-python-client/releases/tag/v1.0.12)

June 27, 2024

https://www.merge.dev/changelog/week-4-june-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, June 2024

# 🖇️

## Integrations

[Zelt HR](https://www.merge.dev/integrations/zelt) for HRIS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667dc8b27e368324b7060cf1_Zelt%20Changelog%20Image.webp)

[Avature](https://www.merge.dev/integrations/avature) for ATS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/667dc8ba85095e048007bcb6_Avature%20Integration%20Changelog.webp)

# 🌎

## APAC Multi-Tentant

Merge is continuing to expand globally to securely support you and your customers’ data residency requirements. We now offer a multi-tenant option in the Asia-Pacific (APAC) region which allows you to store data in AWS data centers in Singapore.

Available to all customers, simply create an account [here](https://app-ap.merge.dev/signup), or, when creating an account on our default sign-up page, select the USA dropdown and click on APAC

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “number” for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Support for “date” for [POST /payments](https://docs.merge.dev/accounting/payments/#payments_create) for Quickbooks Online
- Support for single entity Sage Intacct instances
- Enhancements to  “tracking\_categories” for “line\_items” for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct

##### **🤝**     ATS

- Enhancements to error handling for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for BambooHR
- Support for [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for SAP SuccessFactors
- Support for “screening\_question\_answers” for GET & POST [/applications](https://docs.merge.dev/ats/applications/) for SAP SuccessFactors, Workday and UKG Pro Recruiting

##### **🏠**     HRIS

- Enhancements to [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for 7Shifts
- Enhancements to [employments](https://docs.merge.dev/hris/employments/) and “employment\_status” on [employees](https://docs.merge.dev/hris/employees/) for ADP SFTP
- Enhancements to “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) to Deel
- Enhancements to [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) and [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for UKG Pro

##### **🎟️**     Ticketing

- Enhancements to [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Dixa

##### 📄     Documentation

- Improvements to the calculation of [supported fields](https://docs.merge.dev/integrations/hris/supported-fields/)
- General improvements to docs pages

##### 🎮      Merge Link and Dashboard

- Improved logic for displaying admin needed screen in Merge Link
- Duplicate [Linked Account](https://docs.merge.dev/get-started/linked-account/) detection now available for Admins with or without billing permissions
- Improved UX for when [Free](https://www.merge.dev/pricing) customers hit Linked Account limit

##### 🔄     Syncing Data

- Optimizations for [NetSuite](https://docs.merge.dev/integrations/accounting/netsuite/sync-frequencies/) syncs
- Optimizations for [Justworks](https://docs.merge.dev/integrations/hris/justworks/sync-frequencies/) syncs
- Optimizations for [Gusto](https://app.asana.com/0/1204493048452037/1207594754731143/f) syncs
- Optimizations for [Deleted Data Detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection)
- Improved logic for handling initial vs. subsequent syncs
- Improved logic for sending {common\_model}.synced [webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improved logic for marking an account as [relink needed](https://help.merge.dev/en/articles/6461253-relink-needed-status)

# 👨‍💻

## SDK Updates

- Legacy HRIS Ruby SDK [v3.2.2](https://github.com/merge-api/merge-hris-ruby)

June 20, 2024

https://www.merge.dev/changelog/week-3-june-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, June 2024

# 📂

## File Picker is now available in GA

The File Picker feature is officially available for all File Storage category users. File Picker is built into our embedded Merge Link component and provides a user-friendly interface for your customers to browse and select files and folders in their connected File Storage account.

[Learn more about it in our docs](https://docs.merge.dev/filestorage/file-picker/).

# 🔄

## Selective Sync is available in beta for Google Drive

Your customers can now apply Selective Sync filters for Google Drive folders and drives that they want to sync. Note that this is available in beta. Please reach out to your customer support manager or [support@merge.dev](mailto:support@merge.dev) with any questions.

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “name” for department tracking categories for [GET /tracking-categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for NetSuite

##### **🤝**     ATS

- Support for “location” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Ashby
- Support for attachments on [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for BambooHR
- Support for [POST /candidate](https://docs.merge.dev/ats/candidates/#candidates_create) and “phone\_numbers” for GET /candidate for Occupop
- Enhancements to [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) and [GET /job-interview-stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Occupop

##### **🏠**     HRIS

- Support for “start\_date” and “end\_date” for [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for ADP
- Enhancements to “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Support for “preferred\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Enhancements to “employment\_status” for terminated employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Humi
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors

##### **🎟️**     Ticketing

- Support for “ticket\_url” for epics for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Shortcut
- Enhancements to [GET /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Zendesk

June 13, 2024

https://www.merge.dev/changelog/week-2-june-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, June 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “name” for department tracking categories for [GET /tracking-categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for NetSuite

##### **🤝**     ATS

- Support for “location” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Ashby
- Support for [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for BambooHR
- Support for [POST /candidate](https://docs.merge.dev/ats/candidates/#candidates_create) and “phone\_numbers” for [GET /candidate](https://docs.merge.dev/ats/candidates/#candidates_list) for Occupop
- Enhancements to [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) and [GET /job-interview-stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Occupop

##### **🏠**     HRIS

- Support for “start\_date” and “end\_date” for [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for ADP
- Enhancements to “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Support for “preferred\_name” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Enhancements to “employment\_status” for terminated employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Humi
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors

##### **🎟️**     Ticketing

- Support for “ticket\_url” for epics for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Shortcut
- Enhancements to [GET /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Zendesk

##### 🎮    Merge Link and Dashboard

- Roboto font now available for [Customizable Merge Link](https://app.merge.dev/configuration/link/themes)
- UI improvements for requested data review screen in [Merge Link](https://docs.merge.dev/get-started/link/)
- UX improvements to Selective Sync flows in Merge Link
- UI improvements for loading screens in Merge Link
- UX improvements to [UKG](https://docs.merge.dev/integrations/hris/ukg-pro/sync-frequencies/) and [Workday](https://docs.merge.dev/integrations/hris/workday/sync-frequencies/) flows in Merge Link
- UX improvements to authentication flows in Merge Link
- UI/UX improvements to [Linked Account](https://docs.merge.dev/get-started/linked-account/) Webhooks configuration page in Dashboard
- UI improvements to Linked Account Data Sync page in Dashboard
- UX improvements to Linked Account deletion in Dashboard
- Improvements to [Issue](https://help.merge.dev/en/articles/5389726-issue-tracking) generation for Workday

##### 🔄    Syncing Data

- [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) is now available for [SFTP](https://help.merge.dev/en/articles/9054729-secure-file-transfer-protocol-sftp)
- Efficiency improvements for [NetSuite](https://docs.merge.dev/integrations/accounting/netsuite/sync-frequencies/) syncs
- Efficiency improvements for [UKG Ready](https://docs.merge.dev/integrations/hris/ukg-ready/sync-frequencies/) syncs

June 5, 2024

https://www.merge.dev/changelog/week-1-june-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, June 2024

# 📣

## Merge has established an official partnership with Rippling

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/665a330b73a16acedbd039b1_Rippling%20annonucement%20(2).jpg)

We’re excited to announce that we’ve entered into a formal partnership with Rippling—a leading workforce management system—which will allow clients to integrate their products to Rippling via Merge!

Merge is the first unified API solution to formally partner with Rippling and we see this as a big milestone in supporting our clients’ HRIS integration needs.

[Read more about it here](https://www.merge.dev/blog/partnership-with-rippling) and please reach out to your dedicated Customer Support Manager or [support@merge.dev](mailto:support@merge.dev) if you have any questions!

# 🖇️

## New linking flow step for admin-required HR & ATS integrations

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6660bf66ec4014b7f09cd5db_Admin%20check.webp)

For admin-required HR & ATS integrations, an initial screen will now appear in Merge Link to inform your users they must be an admin of that third-party platform to successfully link. There is also a Magic Link URL that your user can share with the relevant admin, improving the overall user experience auth process!

# 🗾

## New Field Mapping capabilities

[Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) is a flagship feature, enabling you and your customers to map custom data to Merge’s Common Models. We’ve expanded it’s functionality, making it even more powerful and intuitive.

- [**Advanced Mapping**](https://help.merge.dev/en/articles/9269164-advanced-field-mapping-with-jmespath): Map any custom fields in a “list” or “object” format is now supported! Use JMESPath queries to access specific values from even the most complicated remote field objects.
- **Field Coverage:** Easily identify the correct remote field from a customer's account to use when mapping custom fields. Field coverage is a percentage estimate of how often a specific remote field appears for a specific Linked Account. The higher the coverage, the more widely it is used.
- **Preview Values:** Preview and validate that your Field Mapping is accurate before going live. Plug in any Common Model ID to check its return value in the Merge Dashboard.

These features are all now available on our Professional and Enterprise plans. Try them out today and let us know if you have any feedback!

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to syncing for [GET /transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Quickbooks Online
- Enhancements to “company\_id” field in linking flow for Sage Intacct
- Enhancements to [GET /credit-notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) and [GET /vendor-notes](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Sage Intacct
- Enhancements to [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Sage Intacct
- Updated API to reflect domain changes for Zoho Books

##### 🤝    ATS

- Support for .doc and .pdf files in [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for SmartRecruiters
- Enhancements to “source” for candidates for [POST /applications](https://docs.merge.dev/ats/attachments/#attachments_create) for Workable

##### 🏆    CRM

- Enhancements to “amount” for [GET /opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Hubspot

##### 🏠    HRIS

- Enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for terminated employees for BambooHR
- Support for custom fields in “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paycor
- Support to link accounts with multiple subsidiaries for Paylocity
- Enhancements to “start\_time” and “end\_time” for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Personio
- Enhancements to [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for rehired employees for SAP SuccessFactors
- Enhancements to “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### 🎟️    Ticketing

- Support to link accounts via the fine-grained token method for Github
- Support for cycles in [GET /collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Linear
- Enhancements to syncing for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Shortcut

##### 🎮    Merge Link and Dashboard

- Improvements to linking flow for ADP service accounts
- New linking flow steps for when an administrator role is required in the 3rd party platform
- Added [Audit Trail](https://app.merge.dev/audit-trail) event for when end-user API credentials are accessed
- Added Audit Trail event for when a Linked Account is [deleted via API](https://docs.merge.dev/hris/delete-account/)
- UI improvements to [3rd party webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) configuration page in Dashboard

##### 🔄    Syncing Data

- Broad improvements to sync speeds across all integrations
- Support for 3rd party webhooks edge cases
- Support for 3rd party authentication edge cases

May 30, 2024

https://www.merge.dev/changelog/week-5-may-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, May 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “attachments” for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Enhancements to [PATCH /invoices](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) for Sage Intacct

##### 🤝    ATS

- Support for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Avature
- Support for timestamp for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list), [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list), [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list), and [GET /users](https://docs.merge.dev/ats/users/#users_list) for Avature
- Updated Jobscore from V1 to V2 endpoints
- Enhancements to “name” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for UKG Pro Recruiting

##### 🏆    CRM

- Enhancements to [POST /leads](https://docs.merge.dev/crm/leads/#leads_create) for Zoho CRM

##### 🏠    HRIS

- Enhancements to “status” enum for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for BambooHR
- Enhancements to “remote\_data” for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Factorial
- Support for when employees are removed from groups for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Microsoft Entra ID
- Enhancements to “employment\_status” enums for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paycom

##### 🎟️    Ticketing

- Enhancements to [GET /users](https://docs.merge.dev/ticketing/users/#users_list) and [GET /teams](https://docs.merge.dev/ticketing/teams/#teams_list) for Asana

##### 📄    API and Documentation

- Enhancements to [/passthrough](https://docs.merge.dev/supplemental-data/passthrough/making-a-request/) endpoints
- Advanced [Kotlin/JVM SDK v1.0.10](https://github.com/merge-api/merge-java-client/releases/tag/v1.0.10)
- Advanced [Python SDK v1.0.9](https://github.com/merge-api/merge-python-client/releases/tag/v1.0.9)
- Advanced [Go SDK v1.0.8](https://github.com/merge-api/merge-go-client/releases/tag/v1.0.8)
- Advanced [Ruby SDK v0.1.2](https://github.com/merge-api/merge-ruby-client/releases/tag/v0.1.2)
- Advanced [C# SDK v0.0.9](https://github.com/merge-api/merge-csharp-client/releases/tag/0.0.9)

##### 🎮    Merge Link and Dashboard

- UX improvements to Linked Account Webhook Configuration page in Dashboard
- UI improvements to [Integrations](https://app.merge.dev/integrations/hris) page in Dashboard
- UI improvements to Field Mapping page in Dashboard
- UI improvements to Field Mapping flow in Merge Link
- UX improvements to failed linking attempt flows in Merge Link
- General Dashboard UI improvements

##### 🔄    Syncing Data

- Support for datetime field edge cases across integrations
- Support for for edge cases in file return formats from 3rd parties
- Updates to calculating emission for LinkedAccount.synced and CommonModel.synced [webhooks](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improved efficiency for processing [3rd party webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/)
- Enhancements to sync efficiency across integrations

May 22, 2024

https://www.merge.dev/changelog/week-4-may-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, May 2024

# ✨

## Improvements

##### 💰    Accounting

- Support to convert purchase orders to invoices with [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Support to [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) and [POST /purchase-orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for single currency instances in Netsuite

##### 🤝    ATS

- Enhancements to sync performance for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Ashby
- Support for [POST /applications](https://docs.merge.dev/ats/applications/#applications_create), [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create), and [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Bullhorn
- Enhancements to pagination for Fountain
- Enhancements to remote\_date for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Oracle Taleo
- Support for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Tribepad

##### 🏠    HRIS

- Support for a new field to our [Group](https://docs.merge.dev/hris/groups/) common model, name “is\_commonly\_used\_as\_team”. More details on the field [here](https://help.merge.dev/en/articles/7170465-migrating-from-teams-to-groups#h_b7d37e0804)
- Enhancements to “manager” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Enhancements to “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Enhancements to “groups” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Gusto
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Sage HR & Paychex

##### 🎟️    Ticketing

- Enhancements to error messaging for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana

##### 📄    API and Documentation

- Advanced [Node SDK v1.0.8](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.8)
- Efficiency improvements for [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_) endpoint
- Added is\_common\_model\_field as a filter to GET /remote-field-classes endpoints for [CRM category](https://docs.merge.dev/crm/overview/)

##### 🎮    Merge Link and Dashboard

- UI improvements for [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) configuration page in Dashboard
- UI improvements for sync status on [Linked Account](https://docs.merge.dev/get-started/linked-account/) overview page in Dashboard
- UI improvements for [Billing](https://app.merge.dev/billing) page in Dashboard
- UX improvements for [Linked Accounts](https://app.merge.dev/linked-accounts/accounts) page in Dashboard
- Improvements to [Hubspot](https://docs.merge.dev/integrations/crm/hubspot/sync-frequencies/) authentication flow in [Merge Link](https://docs.merge.dev/get-started/link/)
- Improvements to [Google Drive](https://docs.merge.dev/integrations/filestorage/google-drive/sync-frequencies/) authentication flow in Merge Link
- Improvements to [UKG Pro Recruiting](https://docs.merge.dev/integrations/ats/ukg-pro-recruiting/sync-frequencies/) linking flows in Merge Link
- Support for edge cases when generating [Issues](https://help.merge.dev/en/articles/5389726-issue-tracking) for [Paycom](https://docs.merge.dev/integrations/hris/paycom/sync-frequencies/)
- Added events for enabling and disabling [Merge Webhooks](https://docs.merge.dev/basics/webhooks/merge-webhooks/) to [Audit Trail](https://help.merge.dev/en/articles/8813877-merge-audit-trail-enhancing-security-compliance)
- Added events for Field Mapping configuration changes to Audit Trail

##### 🔄    Syncing Data

- Improved rate limit management for [Zendesk](https://docs.merge.dev/integrations/ticketing/zendesk/sync-frequencies/)
- Improvements to [Deleted Data Detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection)
- Support for edge cases in initial syncs for [SAP SuccessFactors](https://docs.merge.dev/integrations/hris/sap-successfactors/sync-frequencies/)
- Support for edge cases in syncs for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/)
- Support for edge cases when zipped files are returned via API from 3rd party platforms

May 16, 2024

https://www.merge.dev/changelog/week-3-may-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, May 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for multi-currency for Netsuite
- Support for "purchase\_orders" for [POST /invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct

##### 🤝    ATS

- Enhancements to performance for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list) for Ashby
- Support for [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for JobAdder
- Support for [GET /job-posting](https://docs.merge.dev/ats/job-postings/#job_postings_list) for Oracle Taleo
- Enhancements to “remote\_data” for [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for UKG Pro Recruiting

##### 🏆    CRM

- Enhancements to error messaging for [GET /notes](https://docs.merge.dev/crm/notes/#notes_list) for Pipedrive

##### 🏠    HRIS

- Enhancements to “country” for “work\_locations” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now
- Enhancements to enums for “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Enhancements to “employment\_status” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Dayforce
- Enhancements to “mobile\_phone\_number” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Dayforce
- Enhancements to “pay\_frequency” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Enhancements to “employments” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Humaans
- Support for terminated employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Enhancements to “locations” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paylocity
- Enhancements to “start\_time” and “end\_time” to support local timezones for [GET /time-off](https://docs.merge.dev/hris/time-off/#time_off_list) for Personio
- Enhancements to “flsa\_status” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Workday

##### **🎟️**    Ticketing

- Enhancements to performance for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Github
- Enhancements to error messaging for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Clickup
- Enhancements to “remote\_data” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Hubspot Ticketing
- Enhancements to error messaging for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Enhancements to enums for “status” for [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira

##### 📄    API and Documentation

- Efficiency improvements for POST endpoints
- Efficiency improvements for [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_) endpoint

##### 🎮    Merge Link and Dashboard

- Linking flow improvements for [ClayHR](https://docs.merge.dev/integrations/hris/clayhr/sync-frequencies/)
- UX improvements for configuring [Scopes](https://app.merge.dev/common-models/hris) in Dashboard
- UI improvements for Linked Account overview page in Dashboard
- UI improvements to Linked Account [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) page in Dashboard
- UI improvements to [Linked Account](https://app.merge.dev/linked-accounts/accounts) and [Issues](https://app.merge.dev/issues?status=ONGOING) filtering in Dashboard
- UI improvements to [3rd Party Webhook](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) configuration in Dashboard
- UI improvements to [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) in Dashboard
- Updates to [Get Started, Webhooks](https://app.merge.dev/get-started/webhooks) page in Dashboard
- Improvements to [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) flows in Merge Link
- Improvements to authentication type selection flows in Merge Link
- Improvements to relinking flows in Merge Link

##### 🔄    Syncing Data

- General improvements for [ADP](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/) syncs
- Improved [deleted data detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection) for [Front](https://docs.merge.dev/integrations/ticketing/front/sync-frequencies/)
- Added support for handling nested lists in [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/)
- Added support for datetime field type edge cases when [mapping fields to common models](https://docs.merge.dev/supplemental-data/field-mappings/overview/)

May 8, 2024

https://www.merge.dev/changelog/week-2-may-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, May 2024

# 🗾

## Advanced Field Mapping with JMESPath

We are continuing to add enhancements to Field Mapping. We released a new enhancement that allows you to write JMESPath queries to access specific values from a list of objects. This will allow you to map any custom fields in a list format to Merge’s Common Models.

Learn more with this [Help Center article](https://help.merge.dev/en/articles/9269164-advanced-field-mapping-with-jmespath).

# ✨

## Improvements

##### 🤝    ATS

- Updated authentication to support clients from Canada for UKG Pro Recruiting
- Enhancements to “applications” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Greenhouse

##### 🏠    HRIS

- Support for “city”, “country”, and “state” for work locations for [GET /locations](https://docs.merge.dev/hris/locations/#locations_list) for ADP Workforce Now
- Enhancements to “effective\_date” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for ADP Workforce Now
- Enhancements to “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Enhancements to “pay\_period” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Support for “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Employment Hero
- Enhancements to “employment\_type” for part time eligible employees for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for Gusto
- Support for GET /time-off and [GET /employee-payroll-runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for Oracle HCM
- Support for custom fields for “remote\_data” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paychex
- Enhancements to “start\_date” for rehired employees for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Paylocity
- Enhancements to “company” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactor
- Support for [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/) edge cases

##### 🎟️    Ticketing

- Enhancements to [GET /users](https://docs.merge.dev/ticketing/users/#users_list) and [GET /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Dixa
- Enhancements to automatic webhooks for Dixa
- Support for [POST /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_create) for Zendesk
- Support for [Dixa](https://docs.merge.dev/integrations/ticketing/dixa/sync-frequencies/) edge cases

##### 🎮    Merge Link and Dashboard

- Enhancements to [Merge Link](https://docs.merge.dev/get-started/link/) loading speed
- Support to open and populate [API Tester](https://help.merge.dev/en/articles/8614547-api-tester-mock-sandbox) directly from logs
- UI improvements to [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) in Dashboard
- General Dashboard UI improvements

##### 🔄    Syncing Data

- Support for additional timezone formats
- Improved reliability for [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) in EU

May 1, 2024

https://www.merge.dev/changelog/week-1-may-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, May 2024

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to "remote\_data" for [GET /tracking-categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for NetSuite
- Support for [POST /attachments](https://docs.merge.dev/accounting/attachments/#attachments_create) for Sage Business Cloud, Sage Intacct, and Xero
- Enhancements to remote\_data for [GET /invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct

##### 🤝ATS

- Support for [GET /attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Ashby
- Support for [GET /job-postings](https://docs.merge.dev/ats/job-postings/#job_postings_list) for Ashby
- Enhancements to “first\_name” and “last\_name” for [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Ashby
- Enhancements to [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for JazzHR
- Expanded support for [GET /applications](https://docs.merge.dev/ats/applications/#applications_list), [GET /candidates](https://docs.merge.dev/ats/candidates/#candidates_list), [GET /jobs](https://docs.merge.dev/ats/jobs/#jobs_list), [GET /jobs/{job\_id}/screening-questions](https://docs.merge.dev/ats/jobs/#jobs_screening_questions_list), [GET /job-interview-stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list), [GET /offers](https://docs.merge.dev/ats/offers/#offers_list), [GET /users](https://docs.merge.dev/ats/users/#users_list), [POST /activities](https://docs.merge.dev/ats/activities/#activities_create), [POST /applications](https://docs.merge.dev/ats/applications/#applications_create), [POST /attachments](https://docs.merge.dev/ats/attachments/#attachments_create), and [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for UKG Pro Recruiting
- Enhancements to “email\_addresses” and “phone\_numbers” for [POST /candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday

##### 🏆CRM

- Enhancements to error handling on [PATCH /contacts/{id}](https://docs.merge.dev/crm/contacts/#contacts_partial_update) for Salesforce

##### 🏠HRIS

- Enhancements to groups for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for CharlieHR
- Enhancements to “phone\_numbers” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for HiBob
- Enhancements to “termination\_date” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Nmbrs
- Enhancements to “personal\_email” and “work\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Updated authentication to support clients from Canada for Zoho People

##### 🎟️Ticketing

- Enhancements to [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list) for Basecamp
- Enhancements to [POST /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Hive
- Support for [POST /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_create) for Intercom
- Support for [POST /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_create) for Zendesk
- Enhancements to “is\_private” for [POST /comments](https://docs.merge.dev/ticketing/comments/#comments_create) for Zendesk

##### 🎮Merge Link and Dashboard

- UI improvements for [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) in [Merge Link](https://docs.merge.dev/get-started/link/)
- UI improvements for SFTP flow in Merge Link
- Improvements to calculation of [Sync Status](https://help.merge.dev/en/articles/5388486-checking-the-sync-status-of-my-integrations)
- General UI improvements for [Field Mapping](https://docs.merge.dev/supplemental-data/field-mappings/overview/) in Dashboard

##### **🔄    Syncing Data**

- Broad optimizations for initial syncs
- Support for edge case in [Ashby](https://docs.merge.dev/integrations/ats/ashby/sync-frequencies/) initial syncs
- Support for edge cases in [ADP Workforce Now](https://docs.merge.dev/integrations/hris/adp-workforce-now/sync-frequencies/) syncs
- Improvements to Merge Link linking flow for sandbox accounts
- Improvements to Merge Link successful linking flow
- Optimizations for [Gusto](https://docs.merge.dev/integrations/hris/gusto/sync-frequencies/) syncs

April 25, 2024

https://www.merge.dev/changelog/week-4-april-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, April 2024

# 🖇️

## Integrations

[JobDiva](https://www.merge.dev/integrations/jobdiva) and [HaileyHR](https://www.merge.dev/integrations/hailey-hr) are now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/662aa6d3882ecc50a1aa1957_JobDiva.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/662aa6e1cee8e64d234e590b_Hailey%20HR.webp)

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “name” to support middle names for [POST /contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Netsuite
- Enhancements to error messaging for [POST /journal-entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Netsuite

##### 🤝    ATS

- Enhancements to “status” for [GET /job-postings](https://docs.merge.dev/ats/job-postings/#job_postings_list) for Greenhouse
- Enhancements to error messaging for missing required fields for [POST /applications](https://docs.merge.dev/ats/applications/) for UKG Pro Recruiting

##### 🏆    CRM

- Support to create new addresses in [POST /contacts](https://docs.merge.dev/crm/contacts/#contacts_create) for Salesforce
- Support for [POST /leads](https://docs.merge.dev/crm/leads/#leads_create) for Zoho CRM

##### 📁    File Storage

- Enhancements to “remote\_created\_at” and “remote\_updated\_at” for [GET /files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive
- Enhancements to “size” for [GET /folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Google Drive

##### 🏠    HRIS

- Enhancements to “gender” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP
- Updated name of Ceridian Dayforce to Dayforce
- Enhancements to “avatar” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Charthop
- Enhancements to "manager" for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Hibob
- Support for inactive and terminated employees in [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for HR Partner
- Support for when employees are removed from groups in [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Keka
- Enhancements to “employee\_number” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for PayCaptain
- Enhancements to “pay\_rate” for [GET /employments](https://docs.merge.dev/hris/employments/#employments_list) for PayCaptain
- Enhancements to “work\_email” and “personal\_email” for [GET /employees](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### 🎟️    Ticketing

- Performance enhancements to [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list), [GET /tags](https://docs.merge.dev/ticketing/tags/#tags_list) and [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Freshdesk
- Performance enhancements to [GET /attachments](https://docs.merge.dev/ticketing/attachments/#attachments_list), [GET /comments](https://docs.merge.dev/ticketing/comments/#comments_list) and [GET /tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Help Scout
- Performance enhancements to [GET /contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Intercom

##### 🎮    **Merge Link and Dashboard**

- Updated Resync button in [Linked Account](https://app.merge.dev/linked-accounts/accounts) Overview page
- Expanded capabilities for modifying query parameters in [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account)
- UX improvements for sandbox linking flows in Merge Link
- UX improvements for configuring webhook receivers
- UI improvements for [Selective Sync](https://help.merge.dev/en/articles/9113654-selective-sync) pages in Merge Link
- [Dashboard](https://app.merge.dev/) UI/UX improvements for Free and Launch customers

##### 🔄    Syncing Data

- Improved performance for [rescyncing accounts](https://help.merge.dev/en/articles/5388905-force-a-linked-account-to-resync-data)
- Support for edge cases in response data types
- Support for edge cases in [SmartRecruiters](https://docs.merge.dev/integrations/ats/smartrecruiters/sync-frequencies/) pagination
- Support for updates to [Ashby](https://docs.merge.dev/integrations/ats/ashby/sync-frequencies/) pagination

# 👨‍💻

## SDK Updates

- [Advanced Python SDK v1.0.8](https://github.com/merge-api/merge-python-client/releases/tag/v1.0.8)
- [Advanced Java (Kotlin/JVM) SDK v1.0.8](https://github.com/merge-api/merge-java-client/releases/tag/v1.0.8)
- [Advanced Node SDK v1.0.7](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.7)
- [Advanced Go SDK v1.0.7](https://github.com/merge-api/merge-go-client/releases/tag/v1.0.7)
- [Advanced Ruby SDK v0.0.4](https://github.com/merge-api/merge-ruby-client/releases/tag/v0.0.4)

April 17, 2024

https://www.merge.dev/changelog/week-3-april-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, April 2024

# **🗾**

## Enhancements to Field Mapping by surfacing coverage percentage

We’re continuing to invest in our Field Mapping feature, and have pushed out new functionality to help you identify the best remote field from a customer’s account to leverage!

We now show the coverage percentage of each remote field, which is a calculation of how often the specific field is returned with a non-null value across that individual linked account.

For example, if you’re looking to map a specific field mapping for our Employee Object, we will show the coverage for each remote field available for mapping, and how often it is a non-null value for Employees.

This enhancement will give you more confidence that you are mapping the correct and most valuable field from a third-party system for a given field mapping!

Access it through the Linked Accounts view in our Dashboard, under the Field Mappings tab.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66201e9365d9f3f36c052c05_Field%20Mapping%20coverage%20%25.png)

# ✨

## Improvements

##### 💰Accounting

- Enhancements to “account” on “line\_items” for [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for QuickBooks Online

##### 🤝ATS

- Enhancements to “job\_status” for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactor
- Enhancements to “status” for [GET/ Job Posting](https://docs.merge.dev/ats/job-postings/#job_postings_list) for Greenhouse

##### 🏆CRM

- Support for [Account](https://docs.merge.dev/crm/accounts/) created, updated, and deleted and [Opportunity](https://docs.merge.dev/crm/opportunities/) created, updated, and deleted webhooks for Hubspot
- Support for “addresses” and “phone\_numbers” for [POST /Account](https://docs.merge.dev/crm/accounts/#accounts_create) for Hubspot

##### 🏠HRIS

- Added performance improvements to [GET /Time Off](https://docs.merge.dev/hris/time-off/) for SAP SuccessFactor
- Support for “employment\_type” = CONTRACTOR for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian Dayforce
- Enhancements to “ssn” and "date\_of\_birth” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for PayCaptain
- Enhancements to “employment\_status” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for HR Partner
- Enhancements to "date\_of\_birth” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Hibob
- Support for filtering [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) by group “name”

##### **📁** File Storage

- Support for filtering [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) by file ”mime\_type”

##### 🎟️Ticketing

- Enhancements to “ticket\_type” for [GET /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Shortcut
- Enhancements to “body” and "is\_private” for [comment](https://docs.merge.dev/ticketing/comments/) webhooks for Zendesk
- Enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Linear

##### 🎮Merge Link and Dashboard

- UX improvements for configuring [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/)
- UI improvements for Linked Account overview page in Dashboard
- UI improvements for [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) in Dashboard
- [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account) Linked Account search improvements
- Improved Dashboard messaging for Bad API Key [Issue](https://app.merge.dev/issues?status=ONGOING) edge cases
- Support for edge case when displaying [Merge Link](https://docs.merge.dev/get-started/link/) for a single integration

##### 🔄Syncing data

- Enhancements to sync reliability for [QuickBooks Online](https://docs.merge.dev/integrations/accounting/quickbooks-online/sync-frequencies/)
- Enhancements to sync reliability for [Shortcut](https://docs.merge.dev/integrations/ticketing/shortcut/sync-frequencies/)
- Support for edge case in return values for [Salesforce](https://docs.merge.dev/integrations/crm/salesforce/sync-frequencies/)

April 10, 2024

https://www.merge.dev/changelog/week-2-april-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, April 2024

# 🖇️

## Integrations

[Jira Data Center](https://www.merge.dev/integrations/jira-data-center) for ticketing is now available in beta! Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6616c878c31e03ec3b07f346_Jira%20Data%20Center.webp)

# ✨

## Improvements

##### 💰Accounting

- Support to authenticate for individual entities for Sage Intacct
- Support for “tracking\_categories” in [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create), [POST /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_create), [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create), [POST /Payments](https://docs.merge.dev/accounting/payments/#payments_create) and [POST /Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for Sage Intacct
- Support for posting objects to different entities across all POST endpoints for Sage Intacct
- Added reliability enhancements to “accounts” for [POST /Expense](https://docs.merge.dev/accounting/expenses/#expenses_create) for Sage Intacct
- Added reliability enhancements for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Enhancements to “net\_amount” for line items on [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Zoho Books
- Support for [GET /Expense](https://docs.merge.dev/accounting/expenses/#expenses_list) for Zoho Books

##### 🤝ATS

- Support for [GET /Job Posting](https://docs.merge.dev/ats/job-postings/#job_postings_list) for Lever, TeamTailor and Greenhouse Job Board
- Support for “type” on [GET /Job](https://docs.merge.dev/ats/jobs/#jobs_list) for Lever, TeamTailor and Greenhouse Job Board
- Support for [GET /Scorecards](https://docs.merge.dev/ats/scorecards/#scorecards_list) for Workday
- Enhancements to "remote\_id" for [GET /Tags](https://docs.merge.dev/ats/tags/#tags_list) for JazzHR
- Support for EU and JP regions in the linking flow for Zoho Recruit
- Enhancements to [POST /Applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for Ashby
- Enhancements to [POST /Activities](https://docs.merge.dev/ats/activities/#activities_create) for candidates with multiple applications for Lever
- Enhancements to “name” on [GET /Job Interview Stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for JazzHR

##### 🏆CRM

- Added performance enhancements to [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Salesforce
- Support to pass in “owner” for [POST /Contact](https://docs.merge.dev/crm/contacts/#contacts_create) for Hubspot

##### 🏠HRIS

- Support for EU and JP regions in the linking flow for Zoho People
- Enhancements to “employment\_status” on [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Expanded “remote\_data” on [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP
- Enhancements to “pay\_period” on [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for Workday

##### 🎟️Ticketing

- Enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Zendesk
- Support to filter tickets by modified date and tags for Front
- Support for "body" in comment webhooks for Zendesk
- Enhancements to “status” for ticket webhooks for Zendesk
- Enhancements to [PATCH /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira
- Enhancements to [GET /tickets/meta/post](https://docs.merge.dev/ticketing/tickets/#tickets_meta_post_retrieve) for Freshservice

##### 🎮Merge Link and Dashboard

- Support for typeahead search for [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account)
- UI improvements to Merge Link

##### 🔄Syncing data

- Improvements to syncing speeds, in particular for initial sync
- Added support for programmatically deleting [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) upon Linked Account deletion, for [Zendesk](https://docs.merge.dev/integrations/ticketing/zendesk/sync-frequencies/) and [Box](https://docs.merge.dev/integrations/filestorage/box/sync-frequencies/) ‍
- Enhancements to [Merge Webhooks](https://docs.merge.dev/basics/webhooks/merge-webhooks/) speed and processing speed for [3rd Party Webhooks](https://docs.merge.dev/basics/webhooks/third-party-webhooks/) ‍
- Support for [Quickbooks Online](https://docs.merge.dev/integrations/accounting/quickbooks-online/sync-frequencies/) webhooks edge case

# 👨‍💻

## SDK Updates

- [Advanced C# SDK](https://github.com/merge-api/merge-csharp-client) is now available

April 2, 2024

https://www.merge.dev/changelog/week-1-april-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, April 2024

# ✨

### **Now available — User Configurable Scopes!**

Give control to your users!

You can now allow users control over their Scopes during the linking flow simply mark the model or field as optional in Dashboard.

Models and fields that are marked as optional will be enabled by default but able to be disabled by your users prior to connecting.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a9405393b3878c995fd12e_660f3ac03eee8fd15419d04c_image%2520(34)%25203%2520(1).webp)

##### **💰    Accounting** ‍

- Enhanced "file\_url" for [GET /Attachments](https://docs.merge.dev/accounting/attachments/#attachments_list) for [Xero](https://docs.merge.dev/integrations/accounting/xero/sync-frequencies/) ‍
- Added reliability enhancements to [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) and [GET /Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for [Sage Intacct](https://docs.merge.dev/integrations/accounting/sage-intacct/sync-frequencies/)

##### **🤝    ATS**

- Support for “current\_stage” in [POST /Application](https://docs.merge.dev/ats/applications/#applications_create) for [SAP](https://docs.merge.dev/integrations/ats/sap-successfactors/sync-frequencies/)
- Support for [GET /Job Postings](https://docs.merge.dev/ats/job-postings/#job_postings_list) and “type” in [GET /Jobs](https://docs.merge.dev/ats/jobs/) for [Lever](https://docs.merge.dev/integrations/ats/lever/sync-frequencies/)
- Enhanced "remote\_data" for [GET /Applications](https://docs.merge.dev/ats/applications/#applications_list) for [Taleo](https://docs.merge.dev/integrations/ats/oracle-taleo/sync-frequencies/)

##### **🏆    CRM**

- Added reliability enhancements to deleted data for [Hubspot](https://docs.merge.dev/integrations/crm/hubspot/sync-frequencies/)
- Updated default scopes to include [crm.objects.custom.read](http://crm.objects.custom.read/) and [crm.schemas.custom.read](http://crm.schemas.custom.read/) for [Hubspot](https://docs.merge.dev/integrations/crm/hubspot/sync-frequencies/) Partner Auth
- Enhanced “company” on [POST /Leads](https://docs.merge.dev/crm/leads/#leads_create) for [Salesforce](https://docs.merge.dev/integrations/crm/salesforce/sync-frequencies/)

##### **🏠    HRIS**

- Enhanced “start\_time” and “end\_time” for [GET /Time Off](https://docs.merge.dev/hris/time-off/#time_off_list) for [Ceredian Dayforce](https://docs.merge.dev/integrations/hris/dayforce/sync-frequencies/)
- Support for "home\_location", "work\_location" and "groups" for future employees in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for [Workday](https://docs.merge.dev/integrations/hris/workday/sync-frequencies/)
- Enhanced "employment\_status" for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for [Humi](https://docs.merge.dev/integrations/hris/humi/sync-frequencies/)
- Enhancements to “display\_full\_name” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for [SAP SuccessFactors](https://docs.merge.dev/integrations/hris/sap-successfactors/sync-frequencies/)
- Added reliability enhancements to [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) and [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for [Nmbrs](https://docs.merge.dev/integrations/hris/nmbrs/sync-frequencies/)

##### **🎫    Ticketing**

- Support to filter tickets by multiple tags for [Intercom](https://docs.merge.dev/integrations/ticketing/intercom/sync-frequencies/)
- Support for webhooks with [Ticket](https://docs.merge.dev/ticketing/tickets/) deleted, [Ticket](https://docs.merge.dev/ticketing/tickets/) archived, [Ticket](https://docs.merge.dev/ticketing/tickets/) reopened [Ticket](https://docs.merge.dev/ticketing/tickets/) assignee updated, [Comment](https://docs.merge.dev/ticketing/comments/) created, and [Tag](https://docs.merge.dev/ticketing/tags/) added events for [Front](https://docs.merge.dev/integrations/ticketing/front/sync-frequencies/)
- Enhancements to [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for [Hive](https://docs.merge.dev/integrations/ticketing/hive/sync-frequencies/)

##### **📄    API and documentation**

- Customer subdomain added to [/linked-accounts](https://docs.merge.dev/hris/linked-accounts/#linked_accounts_list)
- [PATCH Invoice](https://docs.merge.dev/accounting/invoices/#invoices_partial_update) and [PATCH Payments](https://docs.merge.dev/accounting/payments/#payments_partial_update) now available in Beta
- Improvements to [Supported Integrations Fields table](https://docs.merge.dev/integrations/hris/supported-fields/)

##### **🎮    Merge Link and Dashboard**

- Improved UI for log details panel
- Improved styling of Merge Link once it's [embedded](https://docs.merge.dev/get-started/link/#add-merge-link-to-your-product)
- Improved reliability of API Tester when using [Mock Sandboxes](https://app.merge.dev/api-tester/you-to-merge/mock-sandbox)
- Improved calculation of “Next sync start” time on [Linked Account](https://app.merge.dev/linked-accounts/accounts)/Overview page
- [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) UI improvements
- General Dashboard UI improvements
- General Merge Link UI improvements

##### **🔄    Syncing data**

- Improved reliability of [NetSuite](https://docs.merge.dev/integrations/accounting/netsuite/sync-frequencies/) syncs
- Added support for edge case when [mapping common model fields](https://docs.merge.dev/supplemental-data/field-mappings/target-fields/) for [UKG Ready](https://docs.merge.dev/integrations/hris/ukg-ready/sync-frequencies/)
- Improved reliability of [AlexisHR](https://docs.merge.dev/integrations/hris/alexishr/sync-frequencies/) syncs
- Improved reliability of [Bullhorn](https://docs.merge.dev/integrations/ats/bullhorn/sync-frequencies/) authentication

March 26, 2024

https://www.merge.dev/changelog/week-4-march-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, March 2024

# ✨

## Improvements

##### 💰Accounting

- Support for tracking categories for [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for QuickBooks Online
- Added more detailed error messaging for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Further normalized [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Microsoft Dynamics
- Support for country code and area code in [GET /Phone Number](https://docs.merge.dev/accounting/phone-numbers/#phone_numbers_retrieve) for Xero

##### 🤝ATS

- Support for “source” in [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for BambooHR
- Added more detailed error messaging when trying to [POST /Activity](https://docs.merge.dev/ats/activities/#activities_create) to a candidate without any applications for Lever
- [Improved “name” on GET /Attachments for Workable](https://docs.merge.dev/ats/attachments/#attachments_list)
- Support for job posting urls on [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Jobvite and UKG Pro Recruiting
- Support to filter job posts by internal status for Greenhouse
- [Offer](https://docs.merge.dev/ats/offers/) is now expandable on [Application](https://docs.merge.dev/ats/applications/)

##### 🏆CRM

- Added performance enhancements to remote\_fields for [GET /Accounts](https://docs.merge.dev/crm/accounts/), [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), and [GET /Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Hubspot
- Support for better null handling for [POST /Leads](https://docs.merge.dev/crm/leads/#leads_create) for Salesforce

##### 📁File Storage

- Support for shared files and folder in File Picker for OneDrive

##### 🏠HRIS

- Support to sync employments without salary information for Hibob
- Support for terminated employees in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Added reliability enhancements to “type” on [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for Workday
- Added reliability enhancements to “status” on [GET /TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for Workday
- Added reliability enhancements for employees with “status” = pending for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) Workday
- Support to filter employees by employment status for Okta

##### 🎟️Ticketing

- Support for [GET /Roles](https://docs.merge.dev/ticketing/roles/#roles_list) for Aha!, Bitbucket, Height and Teamwork
- Added performance enhancements to all models for Jira
- Added performance enhancements for large accounts for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Shortcut
- Support to filter tickets by tags for Intercom and Zendesk
- Support to filter tickets by modified date for Dixa and Freshdesk
- Support for webhooks with Ticket create, Ticket status update, Ticket assignee update, and Comment create events for Dixa

##### 🎮Merge Dashboard

- Linked Account logs page UI improvements
- UX improvements for [Field Mapping](https://app.merge.dev/configuration/field-mappings/target-fields) in Dashboard
- General Dashboard UI improvements

##### 📄Docs

- Updated code snippets for Node in [Get Started](https://docs.merge.dev/get-started/link/) flow
- UI improvements to _Field support by integration_ section on common model pages
- General documentation updates

##### 🔄Sync performance

- Improved reliability for redaction of remote data based upon [scopes](https://app.merge.dev/common-models/hris)
- Improved speed of webhooks for Zendesk

March 19, 2024

https://www.merge.dev/changelog/week-3-march-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, March 2024

# 🗾

## Common Model Overrides is now available!

As part of our expanding our Field Mapping capabilities, you can now set a third-party field to be mapped and defaulted as Merge’s Common Model. This can be specified at the linked account AND the org level.

As part of this launch, there have been major UX enhancements in how to configure your Field Mapping settings in our Dashboard.

Note that this is only available to our pro and enterprise customers. If you’re interested in learning more, feel free to reach out to your customer support manager!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a943e4f64e722159badc35_65fa1b0003babe90a9cafa04_Common%2520model%2520overrides.webp)

# 🖇️

## Integrations

[Oracle HCM](https://www.merge.dev/integrations/oracle-cloud-human-capital-management-hcm) is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a943e5f64e722159badc39_65fa1b100c32d76bb82bfd9f_HCM.webp)

# 🤝

## New ATS Common Model

We are super excited to announce the [Job Posting Common Model](https://docs.merge.dev/ats/job-postings/)! You can now retrieve the external job board announcements for a specific Job opening.

We have also added “type” on [Jobs](https://docs.merge.dev/ats/jobs/). It’s now easier to distinguish between Requisitions, Profiles, and Postings.

# ✨

## Improvements

##### 💰Accounting

- Support for “type” on [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Netsuite, Dynamics, Sage Intacct, Quickbooks Online, Xero, and Zoho Books
- Support for [GET /Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for nested subsidiaries for Netsuite
- Enhancements to prevent shell contacts for [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Quickbooks Online

##### 🤝ATS

- Support for [GET/ Job Posting](https://docs.merge.dev/ats/job-postings/#job_postings_list) for iCIMs, Greenhouse, SAP, Workday, ORC
- Support for “type” for [GET/ Job](https://docs.merge.dev/ats/jobs/#jobs_list) for iCIMs, Greenhouse, SAP, Workday, ORC
- Updated linking flow to allow end users to select EU accounts for Lever
- Added reliability enhancements for name and location for [GET /Office](https://docs.merge.dev/ats/offices/#offices_list) for Workday

##### 📁File Storage

- Support for shared files and folder in File Picker for OneDrive

##### 🏠HRIS

- Enhanced functionality for when employee’s manager is updated in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR
- Added reliability enhancements to “employment\_type” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian Dayforce
- Added reliability enhancements for employees groups for [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for Deel
- Enhancements to remote data for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Humaans
- Added reliability enhancements to “employment\_status” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Lucca
- Support for auto-approval of timeoff requests for [GET /Timeoff](https://docs.merge.dev/hris/time-off/#time_off_list) for PeopleHR
- Support for maternity and paternity leave absences for [GET /Timeoff](https://docs.merge.dev/hris/time-off/#time_off_list) for PeopleHR
- Support for “birthday” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Personio for EU accounts
- Added reliability enhancements when an employee’s manager is updated in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for UKG pro

##### 🎟️Ticketing

- Support for gitlab groups as collections and “parent\_collection” in [GET /Collection](https://docs.merge.dev/ticketing/collections/#collections_list) for Gitlab
- Support for “reporters” as Users in [GET](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [POST /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira Service Management
- Enhancements to “status” in [PATCH /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira Service Management

##### 🎮Merge Dashboard

- Updated calculation of ”Next sync start” in Linked Account data sync tab
- Improved UX of [Scopes](https://app.merge.dev/common-models/hris)
- General Dashboard UI improvements

##### 📄Docs

- Improved accuracy of [Supported Integration Fields table](https://docs.merge.dev/integrations/hris/supported-fields/)
- General Docs UI improvements

##### 🔄Sync performance

- Enhancements to CRM category performance
- Improved reliability of ”is\_initial\_sync” for [/sync-status](https://docs.merge.dev/hris/sync-status/) endpoint
- Enhanced [/Groups](https://docs.merge.dev/hris/groups/) objects for Workday
- Enhanced [/TimeOff](https://docs.merge.dev/hris/time-off/) objects for PeopleHR

‍

March 12, 2024

https://www.merge.dev/changelog/week-2-march-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, March 2024

# 🖇️

## Integrations

[Tribepad](https://www.merge.dev/integrations/tribepad) for ATS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65f0e939a83018aa10dff77f_Tribepad.webp)

# ✨

## Improvements

##### **💰** Accounting

- Support for credit card refunds in [POST /Expense](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks Online
- Added support for expense memos in [POST /Expense](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks Online
- Updated remote\_data with additional fields for [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Netsuite

##### **🤝** ATS

- Support for “stage\_order” for [GET /Job Interview Stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Support for deleted candidate webhooks for Ashby
- Support for [GET /Offers](https://docs.merge.dev/ats/offers/#offers_list) for Workday
- Support for nested applications for [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday Added reliability enhancements to [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday

##### **📁** File Storage

- Added reliability enhancements for [POST /File](https://docs.merge.dev/filestorage/files/#files_create) for Box

##### **🏠** HRIS

- Enhanced Microsoft Entra linking flow
- Support for “street\_1”, “city”, “state” and “zip\_code” for [GET /Locations](https://docs.merge.dev/hris/locations/#locations_list) for Deel
- Support for “start\_date” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Proliant
- Updated logic for users in probationary period to have an “ACTIVE” employment status for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Added reliability enhancements for deleted manager in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro

##### 🎟️Ticketing

- Support for non-workspace users for [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Asana
- Added reliability enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana
- Added reliability enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Dixa
- Support for groups in [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Gitlab
- Support for “parent\_collection” in [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list) for GitLab
- Support to filter tickets by modified\_date for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Intercom
- Added reliability enhancements to [GET /Accounts](https://docs.merge.dev/ticketing/accounts/#accounts_list) and [GET /Contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Intercom
- Expanded functionality for automatic webhooks for accounts that connect through alternate domains for Jira
- Support for workflows in [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Shortcut
- Support to filter tickets by modified\_date for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Zendesk

##### 🎮    Merge Link & Dashboard

- Improvements to API Tester UI
- Improvements to File Picker UI
- New Audit Trail event type tracking of when a [Test Linked Account](https://docs.merge.dev/get-started/linked-account/) is converted to Production
- New ”Data Access” section in [Get Started flow](https://app.merge.dev/get-started/toggle-scopes)
- Improved UX of setting [Scopes in Dashboard](https://app.merge.dev/common-models/hris)
- General Dashboard UI improvements
- Better issue creation for Salesforce accounts

##### 📄    Docs

- Updated [files/{id}/download](https://docs.merge.dev/filestorage/files/#files_download_retrieve) example response
- Improved accuracy of meta support by integration

##### 🔄    Sync performance

- All [Scopes](https://docs.merge.dev/hris/scopes/) are now turned off by default for new customers
- Improved reliability of common model synced [webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improved accuracy of changed data [webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improved reliability of [deleted data detection](https://help.merge.dev/en/articles/5392795-deleted-data-detection)
- Enhanced [Contact](https://docs.merge.dev/accounting/contacts/) objects for Quickbooks Online
- Improved reliability of [file upload](https://docs.merge.dev/filestorage/files/#files_create)

March 6, 2024

https://www.merge.dev/changelog/week-1-march-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, March 2024

# 🖇️

### Integrations

We are excited to announce [Remote](https://www.merge.dev/integrations/remote) is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65e8ba807a0af0056b09fc7a_Remote%20Integration%20Changelog.webp)

# ✨

## Improvements

##### 🤝    ATS

- Added reliability enhancements for “email\_addresses” and “phone\_numbers” in [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for iCIMs

##### 🏆    CRM

- Support for “street\_1” and “postal\_code” in [POST /Contacts](https://docs.merge.dev/crm/contacts/#contacts_create) for HubSpot
- Added reliability enhancements for deleted data for HubSpot
- Added reliability enhancements for “session\_id” for [POST /Custom Objects](https://docs.merge.dev/crm/custom-objects/#custom_object_classes_custom_objects_create) for Salesforce
- Support for [PATCH /Contacts](https://docs.merge.dev/crm/contacts/#contacts_partial_update) without “email\_address” for Salesforce

##### 🏠    HRIS

- Support for “effective\_date” for [GET /Employment](https://docs.merge.dev/hris/employments/#employments_list) for Personio (note: “effective\_date” is populated based on the date when Merge sees “job\_title” or “pay\_rate” change)
- Updated “employment\_status” to “PENDING” for employees with a future start date for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for BambooHR, Justworks, Personio and Workday
- Support for [GET /Timesheet Entries](https://docs.merge.dev/hris/timesheet-entries/#timesheet_entries_list) for BambooHR, Personio, and TriNet HR Platform
- Updated Zenefits to TriNet HR Platform
- Support for [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for Sesame

##### 🎟️    Ticketing

- Support for “reporters” as Users in [GET](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira Service Management
- Added reliability enhancements “name” [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Intercom

##### 🎮    Merge Link & Dashboard

- Improvements to typeahead components in Dashboard
- Improvements to [integrations](https://app.merge.dev/integrations/hris) page in Dashboard
- Updates to [Merge Link configuration](https://app.merge.dev/configuration/link/configuration) in Dashboard
- UI enhancements to [Logs](https://app.merge.dev/logs/api-requests) and [Issues](https://app.merge.dev/issues?status=ONGOING) in Dashboard
- UI enhancements to [Audit Trail](https://app.merge.dev/audit-trail) and [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account)
- General Dashboard UI improvements
- General Merge Link UI improvements

##### 🔄    Sync performance

- Improvements to calculation of “is\_initial\_sync” field for [Common Model synced webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improvements to reliability of [Linked Account synced webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)
- Improvements to [/sync-status](https://docs.merge.dev/hris/sync-status/#sync_status_list) ”is\_initial\_sync” field calculation

February 28, 2024

https://www.merge.dev/changelog/week-4-february-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, February 2024

# ✨

## Improvements

##### **💰**    Accounting

- Support to [POST /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) with existing invoice numbers for Xero
- Support for “contacts” in [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Sage Intacct

##### **🤝**    ATS

- Support for [GET /Users](https://docs.merge.dev/ats/users/#users_list) for Pinpoint
- Support for “hiring\_managers” and “recruiters” on [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Pinpoint
- Updated remote date to include “StartDate” for [GET /Applications](https://docs.merge.dev/ats/applications/#applications_list) for SAP SuccessFactors
- Added reliability enhancements to [POST /Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Workday
- Added performance enhancements for large linked accounts for SAP SuccessFactors

##### **🏆**    CRM

- Support for “address” in [POST /Contacts](https://docs.merge.dev/crm/contacts/#contacts_create) for Hubspot

##### **📁**    File Storage

- Resolved issues with missing files and folders in File Picker for Sharepoint

##### **🏠**    HRIS

- Updated logic for rehired employees to have an “active” status for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Insperity Premier
- Enhancements to shell employee records in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Proliant

##### 🎟️    Ticketing

- Added webhook support for Conversation.deleted, Conversation.user.created, Conversation.admin.single.created, Conversation.user.replied, Conversation.admin.replied, Conversation.admin.noted, Conversation\_part.redacted events for Intercom
- Enhancements to “updated\_date” for [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list) for Jira
- Enhancements to [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for tickets without custom fields for Jira

##### 🎮    Merge Dashboard and Link

- Improvements to detection of deleted data
- Merge Link improvements
- Improvements to Audit Trail UI
- Added Field Mapping change event types for filtering in Audit Trail
- Links to linked account page added to Audit Trail events
- Improvements to Field Mapping UI in Dashboard
- Improvements to Webhook Logs UI in Dashboard
- Improvements to Advanced Configuration UI in Dashboard

# 👨‍💻

## SDK Updates

- Updated Advanced Python SDK to [v1.0.7](https://github.com/merge-api/merge-python-client/releases/tag/v1.0.7)
- Updated Advanced Java SDK to [v1.0.6](https://github.com/merge-api/merge-java-client/releases)
- Updated Advanced Node SDK to [v1.0.6](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.6)
- Updated Advaned Go SDK to [v1.0.6](https://github.com/merge-api/merge-go-client/releases/tag/v1.0.6)

February 22, 2024

https://www.merge.dev/changelog/week-3-february-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, February 2024

# 🔭

## New “View” and “Edit” mode for Scopes

We’ve added an enhancement to our Scopes feature in the Dashboard. You can now toggle to “view” or “edit” mode to easily see your current Scopes settings and make changes to them.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65d7d2fcd46928d76d73d36c_View%20and%20Edit%20in%20Scopes.webp)

# ✨

## Improvements

##### 💰    Accounting

- Added reliability enhancements to bill line items for exchange rate and total amount for [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct
- Added specific error messaging for null memos in [POST /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Added null handling for [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for NetSuite

##### 🤝    ATS

- Support for “source” in [POST /Application](https://docs.merge.dev/ats/applications/#applications_create) for Cornerstone TalentLink
- Added reliability enhancements to remote\_id in [GET /Applications](https://docs.merge.dev/ats/applications/#applications_list) for JazzHR
- Added reliability enhancements to remote\_id in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for JazzHR
- Added error messaging for missing permissions for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors

##### 🏆    CRM

- Support for emails in [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Salesforce
- Added reliability enhancements to [POST /Leads](https://docs.merge.dev/crm/leads/#leads_create) for Salesforce

##### 📁    File Storage

- Added reliability enhancements to mime\_type for [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for Box

##### 🏠    HRIS

- Added reliability enhancements to [Employees](https://docs.merge.dev/hris/employees/) and [Employments](https://docs.merge.dev/hris/employments/) for ChartHop
- Enhancements to “preferred\_name” in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Okta
- Enhancements to employees without managers in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Workday
- Added reliability enhancements to “employment\_type” in [GET /Employment](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro
- Updated authentication to support clients from India for Zoho People
- Removed malformed [Employee](https://docs.merge.dev/hris/employees/) objects for Proliant

##### 🎟️    Ticketing

- Enhancements to [POST /Comments](https://docs.merge.dev/ticketing/comments/#comments_create) for Azure DevOps
- Added performance enhancements to speed up syncs for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Front
- Enhancements to “updatedDate” for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira

##### 🎮    Merge Dashboard and Link

- [API Tester](https://app.merge.dev/api-tester/you-to-merge/linked-account) now supports adding to POST request body
- Merge Link UI/UX improvements

##### 🔄 Sync performance

- Improved logic for determining is\_initial\_sync value (see [/sync-status](https://docs.merge.dev/hris/sync-status/))
- Improved reliability of sync completed [webhook](https://docs.merge.dev/basics/webhooks/merge-webhooks/)

##### 📄    Docs

- Updated SDK code snippets for [passthrough](https://docs.merge.dev/supplemental-data/passthrough/overview/)

February 13, 2024

https://www.merge.dev/changelog/week-2-february-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, February 2024

# ✨

## Improvements

##### 💰    Accounting

- Resolved issues with null line item IDs for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Quickbooks
- Support for “status” on [GET /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Business Cloud
- Support for [PATCH /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Updated error messaging to more accurately include permission errors in Sage Intacct
- Updated linking to not require unnecessary permissions for Sage Intacct
- Enhancements to "tracking\_categories" for [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Xero

##### **🤝**    ATS

- Added reliability enhancements to “file\_name” for [POST /Attachment](https://docs.merge.dev/ats/attachments/#attachments_create) for Cornerstone TalentLink
- Support for non-resume file types in [GET /Attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for Lever

##### **🏠**    HRIS

- Added reliability enhancements for Gusto
- Support for "pay\_rate" and "pay\_period" for [GET /Employment](https://docs.merge.dev/hris/employments/#employments_list) for Insperity Premier
- Added reliability enhancements for “preferred\_name” in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Okta
- Updated error messaging for missing permissions for [GET /Bank Info](https://docs.merge.dev/hris/bank-info/#bank_info_list) for Paycor
- Added reliability enhancements to “employment\_type” for [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro
- Enhancements to earnings in [Employee Payroll Run](https://docs.merge.dev/hris/employee-payroll-runs/) for UKG Pro
- Support for “manager” when an employee has multiple managers for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Workday

##### **🎟️**    Ticketing

- Updated “status” in [GET /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_list) to more accurately reflect what’s returned from Jira Service Management
- Support to edit tags in [PATCH /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Zendesk

##### 🎮    Merge Dashboard and Link

- Improvements to logs filtering in Dashboard
- Improvements to Field Mapping UX in Dashboard
- Improvements to Merge Link reliability
- Improvements to Merge Link UI
- Enhancements to Deel linking flow

##### 🔄 Sync performance

- Improvements to Linked Account Synced webhook functionality

##### 📄    Docs

- Added Typescript code snippets in Docs

February 6, 2024

https://www.merge.dev/changelog/week-1-february-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, February 2024

# 🖇️

## Integrations

[Cezanne HR](https://www.merge.dev/integrations/cezanne-hr) and HeavenHR are now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c267b1f188e6f702fc5df2_Cezanne%20HR.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/65c267a90fb3ee53c675ecda_Heaven%20HR.webp)

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to “transaction\_date” for [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Xero

##### 🤝    ATS

- Enhancements to "status" for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Support for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Oracle Recruiting Cloud
- Support for "email\_addresses" on [GET /Candidate](https://docs.merge.dev/ats/candidates/#candidates_list) for Oracle Recruiting Cloud
- Enhancements to Oracle Recruiting Cloud

##### 🏠    HRIS

- Enhancements to [GET /Employee Payroll Run](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for UKG Pro
- Enhancements to “work\_location” for [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Okta

##### 🎟️    Ticketing

- Added more detailed error messaging to indicate "team" is required for [POST /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) in Linear
- Ticketing [Remote Fields in beta](https://docs.merge.dev/supplemental-data/remote-fields/overview/)

##### 📄    Docs

- Updated field support by integration section on Common Model / endpoint docs pages
- Docs UI improvements

##### 🎮    Merge Dashboard

- Dashboard Billing page UI improvements

January 30, 2024

https://www.merge.dev/changelog/week-4-january-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, January 2024

# 🖇️

### Integrations

[Kenjo](https://www.merge.dev/integrations/kenjo) for HRIS and [Pinpoint](https://www.merge.dev/integrations/pinpoint) and [Occupop](https://www.merge.dev/integrations/occupop) for ATS are now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a940fba5c6b85dfd3b611b_65bac1a1b59cd16cb5928a54_Kenjo%2520Integration.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a940fba5c6b85dfd3b611f_65bac1b222da9a7f7f643155_Pinpoint%2520Integration.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a940fba5c6b85dfd3b6123_65bac1bfc7ae895a499bacd3_Occupop%2520Integration.webp)

# 🔭

### New Scopes API endpoint in beta

We have just released a [new Scopes API endpoint](https://docs.merge.dev/hris/scopes/#default_scopes_retrieve) to control data access programmatically at an org or Linked Account level. By hitting this endpoint, you can pull your current Scope settings both at the org and Linked Account level and change your Linked Account Scopes.

You can learn more about Scopes [here](https://help.merge.dev/en/articles/5950052-common-model-and-field-scopes).

This feature is currently in beta and available to those on a Professional or Enterprise plan. Please reach out to your Customer Success Manager if you’re interested.

## ✨

### Improvements

##### 💰    Accounting

- Support for [POST /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_create) for Xero

##### 🤝    ATS

- Added more detailed error messaging for posting the same attachment for a given candidate for [POST /Attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for Lever

##### 🏆    CRM

- Improved syncing of custom objects for Salesforce

##### 📁    File Storage

- Support for non-admins to link accounts for Google Drive
- Support for non-admins to link accounts for Box

##### 🏠    HRIS

- Updated [POST /Timeoff](https://docs.merge.dev/hris/time-off/#time_off_create) to respect more 3rd party TimeOff restrictions set in Workday
- Updated logic to more accurately reflect employee changes for [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for JumpCloud
- Support for [GET /Bank Info](https://docs.merge.dev/hris/bank-info/#bank_info_list) for Paycor
- Support for “Street” and “City” in [GET /Locations](https://docs.merge.dev/hris/locations/#locations_list) for Freshteam

##### 📄    Docs

- Updated description of [Groups object](https://docs.merge.dev/hris/groups/)
- Clearer display of integration status in Docs

##### 🎮    Merge Dashboard & Link

- Merge Link Field Mapping UI improvements
- General Link UI improvements
- Clearer display of integrations in Merge Link for test accounts
- API Tester UI improvements
- Improvements to Issues UI
- Improvements to detecting deleted data in 3rd party platforms

# 🧑‍💻

### SDK Updates

- Updated Python SDK to [v1.0.5](https://github.com/merge-api/merge-python-client/releases)
- Updated Node SDK to [v1.0.5](https://github.com/merge-api/merge-node-client/releases/tag/v1.0.5)

January 24, 2024

https://www.merge.dev/changelog/week-3-january-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, January 2024

# 🔭

## Linked Account Scopes in Dashboard

You can easily set granular permissions for all your Common Models and fields for each linked account. Based off your customers’ data security and use case requirements, you can now configure and customize scopes at the linked account level through the Merge Dashboard.

This feature is available on our Professional and Enterprise plans. You can learn more [here](https://help.merge.dev/en/articles/5950052-common-model-and-field-scopes).

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66a940d5425672b97e53b062_65b16150a6d153eeaf0bf0c9_Linked%2520Account%2520Scopes.webp)

## ✨

## Improvements

##### 💰    Accounting

- Enhancements to accurately return “classification” in [GET /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for NetSuite
- Added validation and more detailed error messaging for “types” field for [POST /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_create) for Quickbooks Online
- Support for “parent\_category” for departments in [GET /Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) for Quickbooks Online
- Enhancements to support large accounts for [GET /Balance Sheets](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list) for Quickbooks Online
- Enhancements on [POST /Expense](https://docs.merge.dev/accounting/expenses/#expenses_create) for Xero

##### 🤝    ATS

- Support for [GET /Attachments](https://docs.merge.dev/ats/attachments/#attachments_list), [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list), [GET /User](https://docs.merge.dev/ats/users/#users_list), [GET /Job Interview Stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Oracle Recruiting Cloud
- Support to sync data after a selected start date to support large accounts for Oracle Recruiting Cloud

##### 🏠    HRIS

- Enhancements to return an employee’s manager when the manager is removed for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Ceredian Dayforce
- Support for “preferred\_name” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for TriNet

##### 🎟️    Ticketing

- Improvements to Ticketing sync speeds

##### 📄    Docs

- Updated CRM sub-model example responses in Docs
- Updated SDK snippets in [Get Started](https://docs.merge.dev/get-started/link/) in Docs

##### 🎮    Merge Dashboard & Link

- Improved Linked Account page UI in Dashboard
- Enhancements to JustWorks Service account setup page in Merge Link

January 9, 2024

https://www.merge.dev/changelog/week-2-january-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, January 2024

# 🎨

## Customizable Link is now available in Open Beta

Have control over how Merge Link appears to your customers now with Customizable Link, now available on our enterprise plan in open beta. You can customize themes, including fonts, button backgrounds and text colors on Merge Link. You can also replace our default help center articles with your own for any integration within Merge Link.

Customizable Link offers greater control over Merge Link, allowing you to align the component with your brand and share important information seamlessly in the linking flow process.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/659d80845171682ccaf8a3ca_Screenshot%202024-01-09%20at%2010.40.42%E2%80%AFAM.webp)

# 🪝

## Multiple Webhook types now can send to a single URL

Rather than having to associate individual webhooks to separate URLs, you are now able to select different webhook types to send to a single URL. This means you’ll now be notified  in a single place.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/659d80e7e9ce19ee909db6a0_image%20(7).webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for “remote\_id” for [GET /Tax Rate](https://docs.merge.dev/accounting/tax-rates/#tax_rates_list) for Xero

##### 🤝    ATS

- Enhancements to “status”, “remote\_created\_at” and “remote\_updated\_at” for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for JobAdder

##### 📁    File Storage

- Improvements to File Picker UI

##### 🏠    HRIS

- Support for “employee\_number” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Insperity
- Support for “username” [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors; note that it will only populate if the employee has a start date
- Added logic to update an employee’s groups when an employee charges departments for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Zoho People

##### 📄    Docs

- Improvements to SDK pages UX in Docs

##### 🎮    Merge Dashboard & Link

- Improvements to detecting deleted data in 3rd party platforms
- Enhancements to Common Model page UI in Dashboard
- Improvements to HiBob linking flow
- Improvements to sync status accuracy
- Improvements to Dashboard UI

January 3, 2024

https://www.merge.dev/changelog/week-1-january-2024

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, January 2024

# 🪝

## Linked Account synced webhook and Linked Account deleted webhook

Linked Account synced and Linked Account deleted are new webhooks to accurately notify you when certain actions are taken with a specific Linked Account. This is now available to all customers.

- The Linked Account synced webhook will notify you when _all_ Common Models are done syncing.
- The Linked Account deleted webhook will notify you when a Linked Account has been deleted.

We have also added a new field "account\_type” to our webhooks that allow you to differentiate when it’s a Production or Test Linked Account.

# 🖇️

## Integrations

[IRIS Cascade](https://www.merge.dev/integrations/iris-cascade) is now available in beta for our HRIS Unified API. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6595cbc58d7ee76728b53195_IRIS%20Cascade.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for “purchase\_orders” on [POST /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Support for [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for NetSuite
- Enhancements to tracking categories to populate correctly for [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks
- Enhancements to [POST /Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/) for Quickbooks
- Support for transfers in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Sage Intacct
- Support for [POST /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Sage Intacct
- Support for [POST /Payments](https://docs.merge.dev/accounting/payments/#payments_create) for Sage Intacct
- Support for [POST /Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/) for Sage Intacct

##### 🤝    ATS

- Support for [POST /Application Change Stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for BambooHR

##### 🏆    CRM

- Added “owner” field on [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list) for Hubspot, Pipedrive, Salesforce, and ZohoCRM

##### 📄    Docs

- Enhancements to Docs UI

##### 🎮    Merge Dashboard & Link

- Enhancements to Webhook UI in Dashboard
- Improvements to Field Mapping functionality in Merge Link

December 26, 2023

https://www.merge.dev/changelog/week-4-december-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, December 2023

# ✨

## Improvements

##### 💰    Accounting

- Enhancements made to [POST /Expense](https://docs.merge.dev/accounting/expenses/#expenses_create) error handling for QuickBooks Online
- Enhancements to [Journal](https://docs.merge.dev/accounting/journal-entries/) lines for Sage Intacct
- Enhancements to Custom Fields for NetSuite

##### 🏠    HRIS

- Fixed issue with stale manager values for ADP Workforce Now
- Added reliability enhancements to [Location](https://docs.merge.dev/hris/locations/) for ADP Workforce Now
- Added deduping logic to [Groups](https://docs.merge.dev/hris/groups/) for ADP Workforce Now
- Added reliability enhancement to [Employment](https://docs.merge.dev/hris/employments/) currency for Workday

##### 🏆    CRM

- Added reliability enhancement to [Contacts](https://docs.merge.dev/crm/contacts/) for Hubspot

December 19, 2023

https://www.merge.dev/changelog/week-3-december-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, December 2023

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to custom enduser date time configuration affecting [Contacts](https://docs.merge.dev/accounting/contacts/) in NetSuite

##### 🤝    ATS

- Added reliability enhancements to [Interview](https://docs.merge.dev/ats/interviews/) for Oracle Taleo

##### 🏠    HRIS

- Enhancements made to Microsoft Entra ID [Employee](https://docs.merge.dev/hris/employees/) Remote data
- Added reliability enhancements to [Time off](https://docs.merge.dev/hris/time-off/) for Personio
- Enhancements to [Employee](https://docs.merge.dev/hris/employees/) common model for ADP
- Fixed issues with duplicate [Employments](https://docs.merge.dev/hris/employments/) for Insperity Premiere
- Enhancements to [Groups](https://docs.merge.dev/hris/groups/) for Namely
- Enhancements to [Locations](https://docs.merge.dev/hris/locations/) for Paylocity
- Enhancements to [Locations](https://docs.merge.dev/hris/locations/) for Rippling
- Added reliability enhancements to [Employments](https://docs.merge.dev/hris/employments/) for Workday

##### 🎟️    Ticketing

- Added reliability enhancements to [Comments](https://docs.merge.dev/ticketing/comments/) for Dixa
- Added reliability enhancements to [POST/ Comment](https://docs.merge.dev/ticketing/comments/#comments_create) for Zendesk
- Enhancements to Author association with a Comment for Zendesk

##### 📁    File Storage

- Add reliability and efficiency improvement to Box

December 12, 2023

https://www.merge.dev/changelog/week-2-december-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, December 2023

# 🖇️

## Integrations

[Zoho People](https://www.merge.dev/integrations/zoho-people) is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/658de8cb1815cdd2c2a64516_Zoho%20People.webp)

# ✨

## Improvements

##### 💰    Accounting

- Added reliability enhancements to “account” for [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for NetSuite
- Updated to handle larger accounts for [GET /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for Quickbooks Online
- Added reliability enhancements for “number” in [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) for NetSuite
- Support for inactive items for [GET /Items](https://docs.merge.dev/accounting/items/#items_list) for Quickbooks Online
- Support for “sales\_account” for [GET /Items](https://docs.merge.dev/accounting/items/#items_list) for Quickbooks Online
- Added reliability enhancements for deleted payments in [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Xero

##### 🤝    ATS

- Support for [GET /Eeoc](https://docs.merge.dev/ats/eeocs/#eeocs_list) for Workday

##### 🏠    HRIS

- Support for contractors for [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for ADP Workforce Now
- Fixed issues with incorrect groups being added to employees for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for TriNet
- Added more detailed error messaging for [POST /Employee](https://docs.merge.dev/hris/employees/#employees_create) for IntelliHR
- Added reliability enhancements to handle larger accounts for [GET /TimeOff](https://docs.merge.dev/hris/time-off/) for BambooHR
- Support for “name” for work locations for [GET /Location](https://docs.merge.dev/hris/locations/) for Rippling
- Added reliability enhancements to name for [GET /Location](https://docs.merge.dev/hris/locations/) for Paylocity

##### 🎟️    Ticketing

- Support for “is\_active” for [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Freshdesk
- Added reliability enhancements to “author” on [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list) for Zendesk

December 5, 2023

https://www.merge.dev/changelog/week-1-december-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, December 2023

# 🎟️

## Ticketing Roles Now Available!

We are super excited to announce the [Roles Common Model](https://docs.merge.dev/ticketing/roles/)! You can now restrict end-user access to tickets depending on the restrictions set in the native 3rd-party ticketing platform.

We have also added “Access\_level” on [Collections](https://docs.merge.dev/ticketing/collections/). You can now restrict ticket access based on Collection access level and users associated with a collection. Let us know if you have any feedback!

# 🖇️

## Integrations

[Employment Hero](https://www.merge.dev/integrations/employment-hero) and [Humi](https://www.merge.dev/integrations/humi) for HRIS are now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656f741f1c4ddd980a323811_Employment%20Hero%20Changelog.webp)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/656f7412d94739c6ec6ab096_Humi%20Changelog.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for “description” on line items for [POST /Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for NetSuite
- Support for “purchase\_order\_number” in the response for [POST /Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for NetSuite
- Added reliability enhancements to “account” on [GET /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list) for NetSuite
- Added reliability enhancements to support large accounts for [GET /IncomeStatements](https://docs.merge.dev/accounting/income-statements/#income_statements_list) for QuickBooks Online
- Support for “memo”, “currency” and “exchange\_rate”, “tracking\_categories” and “contacts” on line items on [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for QuickBooks Online
- Added logic to not prevent duplicates for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Xero

##### 🤝    ATS

- Support for “recruiters” and “hiring\_manager” for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Workable

##### 📁    File Storage

- Support for Read-Only permissions for OneDrive
- Updated logic only created “permission” for valid users records for [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive and SharePoint
- Support for deleted data in [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for SharePoint

##### 🏠    HRIS

- Support for “groups” on [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for 7Shifts
- Added reliability enhancements for “employment\_status” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian Dayforce
- Support for [GET /Bank Info](https://docs.merge.dev/hris/bank-info/#bank_info_list) for Hibob
- Support for “preferred\_name” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks and Sapling
- Updated logic to only return active “groups” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Okta

##### 🎟️    Ticketing

- Added optimizations to handle rate limiting for Zendesk

November 28, 2023

https://www.merge.dev/changelog/week-5-november-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, November 2023

# ✨

## Improvements

##### 💰    Accounting

- Added additional fields to "remote\_data" for [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for NetSuite
- Updated "line\_items" to include individual sales lines items for Sales Receipts and Refund Receipts in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for QuickBooks Online
- Added reliability enhancements to support large accounts for [GET /Income Statement](https://docs.merge.dev/accounting/income-statements/#income_statements_list) for QuickBooks Online
- Surfaced Merge ID for all line items for accounting objects ( [Expenses](https://docs.merge.dev/accounting/expenses/), [Credit Notes](https://docs.merge.dev/accounting/credit-notes/), [Journal Entries](https://docs.merge.dev/accounting/journal-entries/), [Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/), [Transactions](https://docs.merge.dev/accounting/transactions/), and [Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/))

##### 🤝    ATS

- Added reliability enhancements to [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for SAP SuccessFactors

##### 🏆    CRM

- Added reliability enhancements to [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Salesforce

##### 📁    File Storage

- Support for “file\_url” for PDFs file types in [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive
- Support for “mime\_type” as a query parameter to specify export format on [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for Google Drive

##### 🏠    HRIS

- Support to “base\_ pay” for contractor employment type in [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for Workday
- Enhancements to "remote\_data" for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Google Workspace

November 21, 2023

https://www.merge.dev/changelog/week-4-november-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, November 2023

# 🏖️

## Mock Sandbox and Inbound Request API Tester

Mock Sandbox and Inbound Request API Tester is now available in beta. Now you can test any Merge integration with mock data before deploying them in production to your customers. With Mock Sandbox and API Tester, you can see Merge's normalized responses, reducing the need to have third-party sandbox access.

We are starting with all HRIS integrations but will continue to expand to other categories soon!

[Try it out now](https://app.merge.dev/api-tester/you-to-merge/linked-account) and checkout our [Help Center article](https://help.merge.dev/en/articles/8614547-api-tester-mock-sandbox) to learn more.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655cfbf11d08c80301b91c88_Screenshot%202023-11-15%20at%203.14.09%20PM.webp)

# 🖇️

## Integrations

[Cyberark](https://www.merge.dev/integrations/cyberark) for HRIS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655d099b5d4494470eb76e87_CyberArk.webp)

# ✨

## Improvements

##### 📄    Docs

- [Example request code snippets](https://docs.merge.dev/hris/employees/) are now available in our docs. You can easily copy and paste to easily make API requests to Merge. We currently support Python but are planning on supporting additional languages including cURL and Java in the coming quarter.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/655cfc09e6555740962d124c_image%20(6).webp)

##### 💰    Accounting

- Support for “status” on for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Dynamics
- Support for “description” for [GET /Account](https://docs.merge.dev/accounting/accounts/#accounts_list) for Quickbooks Online
- Support for “applied\_date” on line items for [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Quickbooks Online
- Support for “status” on for [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Sage Intacct
- Support for “applied\_amount” and “applied\_date” on line items for [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Xero

##### 🤝    ATS

- Support for [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for Ashby
- Added clearer error messaging when posting a resume to a candidate with an existing resume for [POST /Attachment](https://docs.merge.dev/ats/attachments/#attachments_create) for iCIMs
- Enhancement to “hiring\_manger” and “recruiter” for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Support for [POST /Attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for SmartRecruiters

##### 🏆    CRM

- Enhancements to “owner”, “due\_date”, “subject”, and “opportunity” for [POST /Task](https://docs.merge.dev/crm/tasks/#tasks_create) for Pipedrive

##### 📁    File Storage

- Enhancements to capturing files through various sharing methods for [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive

##### 🏠    HRIS

- Support for “preferred\_name” for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now
- Support to return “balance” in hours for [GET /TimeOffBalance](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) for BambooHR
- Support for “country” for [GET /Location](https://docs.merge.dev/hris/locations/#locations_list) for Ceridian Dayforce
- Enhancements to only return employees who are active in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Google Workspace
- Support for “country” for [GET /Location](https://docs.merge.dev/hris/locations/#locations_list) for Hibob
- Support for “termination\_date” based on the date when a users status changes to suspended/deprovisioned for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Jumpcloud, OneLogin, Okta, PingOne, and Google Workspace
- Enhancements to return “start\_time” and “end\_time” in local timezone for [GET /TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for Personio
- Enhancements to linking flow instructions for Workable

##### 🎟️ Ticketing

- Support for “is\_active” in [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Basecamp
- Enhancements for large responses for [GET /Accounts](https://docs.merge.dev/ticketing/accounts/#accounts_list) for Intercom
- Support for [POST /Comments](https://docs.merge.dev/ticketing/comments/#comments_create) for Jira Service Management
- Updated “is\_private” to default to false for [POST /Comments](https://docs.merge.dev/ticketing/comments/#comments_create) for Jira Service Management
- Support for "cancelled\_at", "archived\_at", and "creator" in remote\_data for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Linear

November 14, 2023

https://www.merge.dev/changelog/week-3-november-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, November 2023

# ✨

## Improvements

##### 📄    Docs

- Enhancements to docs nav bar with a new "Resources" tab featuring the [Help Center](https://help.merge.dev/en/) and merge.dev

##### 💰    Accounting

_Payments Update:_ We have updated our Payment model with "apply\_to\_lines" that will support applying a singular payment to multiple transactions. This update will improve our Accounts Payable use case. This change is applicable to Xero, Sage Intacct, QBO and Netsuite, with Zoho Books, Microsoft Dynamics, and Freshbooks coming later!

As part of this update we will be eventually deprecating top level “invoice”, “journal\_entry” and “credit\_note” fields on GET/Payments. These fields will remain on POST/ Payments until a future date.

- Support for “location” in [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for NetSuite
- Support for [GET /Purchase Order](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET /Transaction](https://docs.merge.dev/accounting/transactions/#transactions_list) (for Sales Orders and Purchase Requisition) and [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list) for Sage Intacct
- Enhancements to passthrough for PATCH /invoices and DELETE /invoices for Xero
- Enhancements to data quality to “currency” in [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Quickbooks Online
- Enhancements to “company” on line items of [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), and [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Sage Intacct
- Support for deleted line items on [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Sage Intacct
- Enhancements to [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Sage Intacct
- Support for “company\_info” and “contact” on line items for [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Sage Intacct

##### 🤝    ATS

- Added sync enhancements for [GET /Applications](https://docs.merge.dev/ats/applications/#applications_list) and [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Bullhorn
- Support for [GET /Users](https://docs.merge.dev/ats/users/#users_list) for Bullhorn
- Added detailed error messaging for duplicate email addresses in [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for Workable

##### 📁    File Storage

- Added detailed error messaging in [GET /files/{id}/download](https://docs.merge.dev/filestorage/files/#files_download_retrieve) for Box, Dropbox, Google Drive, OneDrive, SharePoint
- Added sync enhancements to [GET/ Files](https://docs.merge.dev/filestorage/files/#files_list), [GET/ folders](https://docs.merge.dev/filestorage/folders/#folders_list), [GET/ Drives](https://docs.merge.dev/filestorage/drives/#drives_list), [GET/ Groups](https://docs.merge.dev/filestorage/groups/#groups_list), and [GET/ Users](https://docs.merge.dev/filestorage/users/#users_list) for Box, Dropbox, Google Drive, OneDrive, SharePoint

##### 🏠    HRIS

- Enhancements to “job\_title” in [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for SAP SuccessFactors
- Support for pending hires in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Enhancements to “employment\_status” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors
- Support for additional status types in “employment\_status” for [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for Ceridian Dayforce
- Support for pay\_currency, pay\_period and pay\_rate for [GET/ Employments](https://docs.merge.dev/hris/employments/#employments_list) for Insperity Premier (Note: will only be returned if your customers have permission for Insperity Employee Compensation)
- Enhancements to “employment\_status” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now
- Support for “preferredName” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now

November 7, 2023

https://www.merge.dev/changelog/week-2-november-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, November 2023

# ✨

## Improvements

##### 💰    Accounting

- Support for "issue\_date" for bills in [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Sage Intacct

##### 🤝    ATS

- Support for [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for Ashby
- Support for "applied\_at" in [GET /Application](https://docs.merge.dev/ats/applications/#applications_list) for Oracle Taleo

##### 🏆    CRM

- Enhanced error messaging for [POST /Notes](https://docs.merge.dev/crm/notes/#notes_create) for Salesforce

##### 📁    File Storage

- Support for non-admins to link accounts for SharePoint

##### 🏠    HRIS

- Enhancements to linking sandbox accounts for Gusto

November 1, 2023

https://www.merge.dev/changelog/week-1-november-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, November 2023

# **✨**

## Improvements

- Improvements to our [Common Model overview pages](https://docs.merge.dev/hris/overview/) which now includes information on authentication, sync frequency, rate limits, and more
- [Audit Trail via API](https://docs.merge.dev/hris/audit-trail/) is now available for Enterprise customers


##### 💰    Accounting

- Support for “sub\_total” and "total\_tax\_amount” in [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks Online
- Enhancements to [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Quickbooks Online
- Enhancements to validation for [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks Online
- Support for “account” on line items in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for NetSuite

##### 🤝    ATS

- Enhancements to syncing “name” for [GET /Job Interview Stages](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Support for [POST /Applications](https://docs.merge.dev/ats/applications/#applications_create) for SmartRecruiters
- Support for [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for BambooHR
- Support for deleted data for “departments” on [GET /Job](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors

##### 🏠    HRIS

- Enhancements to mark “employment\_status” as active for employees who have Not in Payroll status in [GET /Employment](https://docs.merge.dev/hris/employments/#employments_list) for UKG Ready
- Support for “employee\_number” in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Humaans
- Enhancements to “name” in [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for Ceridian Dayforce

##### 🎟️    Ticketing

- Support for [PATCH /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira Service Management
- Enhancements to [GET /tickets/meta/patch/{id}](https://docs.merge.dev/ticketing/tickets/#tickets_meta_patch_retrieve) to include available status change options for a given ticket for Jira Service Management
- Support for sections in [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Asana

October 24, 2023

https://www.merge.dev/changelog/week-4-october-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, October 2023

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to "addresses" to auto-expand on [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list)
- Enhancements to more accurately classify tracking categories in [POST /Payments](https://docs.merge.dev/accounting/payments/#payments_create) for Netsuite
- Added sync optimizations to reduce sync time for Netsuite
- Support for discounts as line items in [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Quickbooks Online
- Support for "sub\_total" and "total\_tax\_amount" on [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for Quickbooks Online
- Added sync optimizations to reduce sync time for [GET /Income Statements](https://docs.merge.dev/accounting/income-statements/#income_statements_list), [GET /Balance Sheets](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list), and [GET /Cash Flow Statements](https://docs.merge.dev/accounting/cash-flow-statements/#cash_flow_statements_list) for Quickbooks Online
- Added sync optimizations to reduce sync time for [GET /Income Statements](https://docs.merge.dev/accounting/income-statements/#income_statements_list), [GET /Balance Sheets](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list), and [GET /Cash Flow Statements](https://docs.merge.dev/accounting/cash-flow-statements/#cash_flow_statements_list) for Xero

##### 🤝    ATS

- Support for “department” in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for iCIMS

##### 🏆    CRM

- Enhancements to “websites” in [GET /Accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for Hubspot

##### 🏠    HRIS

- Support for updated departments in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Justworks
- Added transient error handling to allow for continued syncs for UKG Pro

##### 🎟️    Ticketing

- Enhancements to assignees being properly added to tickets in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira
- Added sync enhancements to [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list) for ServiceNow

October 17, 2023

https://www.merge.dev/changelog/week-3-october-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, October 2023

# ✨

## Improvements

##### 📄    Documentation

- New [syncing data](https://docs.merge.dev/basics/syncing-data/) basic guide to give an overview of how we sync data between you and Merge
- Scrollable [Custom Objects](https://docs.merge.dev/supplemental-data/custom-objects/) code snippets
- onExit and onSuccess information included for [Merge Link](https://docs.merge.dev/get-started/link/#step-2)

##### 💰    Accounting

- Enhancements to sales receipts transaction types for [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Quickbooks Online
- Enhancements to “net\_amount” in line items of [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Workday
- Enhancements to “transaction\_date” in [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Xero
- Updated logic to mark voided credit notes at deleted in [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Xero

##### 🤝    ATS

- Enhancements to null values in “Code" in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Support for [GET /Offers](https://docs.merge.dev/ats/offers/) for Teamtailor
- Enhancements to linking account flow for Bullhorn

##### 📁    File Storage

- Enhancements to “name” in [GET /Groups](https://docs.merge.dev/filestorage/groups/) for Sharepoint
- Support for detailed error messaging when a file name is invalid in [POST /Files](https://docs.merge.dev/filestorage/files/#files_create) for Sharepoint

##### 🏠    HRIS

- Enhancements to “preferred\_name” in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list) for Paylocity

##### 🎟️    Ticketing

- Enhancements to collections not being properly assigned to tickets in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Jira

##### 🏆    CRM

- Enhancements to “phone\_numbers” in [GET /Accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for Salesforce
- Enhancements to “website” on [GET /Accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for Hubspot
- Enhancements to “email\_addresses”, “addresses”, and “phone\_numbers” in [GET /Leads](https://docs.merge.dev/crm/leads/#leads_list)

October 3, 2023

https://www.merge.dev/changelog/week-1-october-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, October 2023

# 🪝

## Account Linked Webhook and Common Model Synced Webhook

Our new [Merge Webhooks](https://docs.merge.dev/basics/webhooks/merge-webhooks/), Account Linked and Common Model Synced, are improved webhooks to accurately and reliably notify you when initial and following syncs are complete, ensuring that data is ready to be pulled.

- The Account Linked webhook will notify you when one of your customers create a new linked account, passing along the necessary account token.
- The Common Model Synced webhook will alert you when that specific Common Model and related fields for a linked account is initially synced and updated after that.

# 📄

## Supported Integrations Features in Docs

Easily see and compare which features, such as deleted data and webhooks, are supported for each integration in [our docs](https://docs.merge.dev/integrations/hris/supported-features/)! The “Supported Integrations Features” table has filtering functionality so you can just look at what integrations and Common Models you care about. Check it out!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/651dc34770a2a7393353f8ab_Supported%20Features%20Table.webp)

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to decrease sync time for [GET /Attachments](https://docs.merge.dev/accounting/attachments/#attachments_list) for Xero
- Support for archived contacts in [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Xero

##### 🤝    ATS

- Support for “description” and “offices” in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Comeet

##### 🏠    HRIS

- Updated logic to only include “manager” if the manager’s effective end date is in the future or null [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian Dayforce
- Updated logic to set “work\_location” from “homeWorkLocation” (if null, will use assignedWorkLocation) in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP

##### 🎟️    Ticketing

- Support for webhooks for Task Created, Task Status Changed, Task Importance Changed, Task Dates Changed, Attachment Added, Comment Added, Task Deleted, Folder Deleted, and Comment Deleted events for Wrike

##### 🏆    CRM

- Sync optimizations to support large syncs for [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list) for Hubspot
- Support for Remote Fields in [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list) and [GET /Leads](https://docs.merge.dev/crm/leads/#leads_list) for Zoho CRM

‍

September 26, 2023

https://www.merge.dev/changelog/week-4-september-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, September 2023

# ✨

## Improvements

##### 💰    Accounting

- Enhancements to decrease sync time and reduce errors for [GET /PurchaseOrders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET /JournalEntries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list), [GET /CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET /Item](https://docs.merge.dev/accounting/items/#items_list), [GET /Payments](https://docs.merge.dev/accounting/payments/#payments_list), [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Microsoft Dynamics 365 Business Center
- Added “remote\_id” as an integration parameter to [POST /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) to be able to link contacts to multiple subsidiaries for NetSuite
- Enhancements to the NetSuite linking flow to streamline the process of creating roles by using an import bundle

##### 🤝    ATS

- Updated remote data for [POST /applications/{id}/change-stage](https://docs.merge.dev/ats/applications/#applications_change_stage_create) for Workable
- Support for “type” as an integration parameter for [POST /Activities](https://docs.merge.dev/ats/activities/#activities_create) for Ashby

##### 🏠    HRIS

- Updated logic for “work location” to pull more unique locations for [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for Ceridian Dayforce
- Support for additional fields in remote data in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for OneLogin
- Enhancements to [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for BambooHR
- Updated “effective date” to more accurately pull start dates in [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) for Workday

##### 🎟️    Ticketing

- Support for remote data in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for non-admin accounts for Jira
- Support for tickets with null projects for [PATCH /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Jira

##### 🏆     CRM

- Added sync optimizations to [GET /Contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list) for Hubspot

September 20, 2023

https://www.merge.dev/changelog/week-3-september-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, September 2023

# 🖇️

## Integrations

[Bullhorn](https://www.merge.dev/integrations/bullhorn) for ATS is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/650b1cd8f56804b2b8aca81d_Blog%20-%20Bullhorn.webp)

# ✨

## Improvements

##### 📄    Documentation

- Brand new [Remote Fields doc](https://docs.merge.dev/supplemental-data/remote-fields/overview/), giving a comprehensive overview of pulling and pushing data

##### 💰    Accounting

- Support for “classification” in [GET /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_list) for FreeAgent
- Enhancements to “balance” to return in the currency of the transaction in [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Netsuite
- Enhancements to “value” in “non-operating expenses” to be negative in [GET /Income Statements](https://docs.merge.dev/accounting/income-statements/#income_statements_list) for Xero
- Support support for deleted transactions and transaction lines in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list), [GET /Purchase Order](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list), [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Xero

##### 🤝    ATS

- Sync enhancements to [GET /Interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Greenhouse
- Support for additional fields to remote data for [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors

##### 📁    File Storage

- Support for shared files in [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for OneDrive
- Sync enhancement and support for deleted files in [GET /Files](https://docs.merge.dev/filestorage/files/#files_list) for Box

##### 🏠    HRIS

- Enhancements to “effective\_date” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for TriNet

##### 🎟️    Ticketing

- Sync optimizations to [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list) and [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Asana
- Enhancements to logic to include board members and guests in [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Trello

##### 🏆    CRM

- Added enhanced error messaging for [POST /Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_create) for Salesforce

‍

September 12, 2023

https://www.merge.dev/changelog/week-2-september-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, September 2023

# 🖇️

## Integrations

[Hubspot Ticketing](https://www.merge.dev/integrations/hubspot-ticketing) for Ticketing is now available in beta. Please reach out to your Customer Support Manager if you’d like to get access and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6500d0f6c33221dbd982ca50_Blog%20-%20Hubspot%20Ticketing.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for “status” on [GET /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list) for FreshBooks
- Support for “purchase order” on [GET /Purchase Order](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list) for QuickBooks Online, Xero, Dynamics, and NetSuite
- Support for “tracking categories” on [POST /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for NetSuite
- Support for “tracking categories” on [POST /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for Quickbooks Online

##### 🤝    ATS

- Support for “job\_posting\_urls” in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for JazzHR
- Support for candidate fields “sourced\_by”, “source, job”, “current\_stage” and application fields “emails”, “phones”, “tags” “URLs” in the response of [POST /Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Lever

##### 🏠    HRIS

- Enhanced error handling and reliability for [POST /Employees](https://docs.merge.dev/hris/employees/#employees_create) for IntelliHR
- Support for remote data in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for AlexisHR
- Updated logic to return phone number without country codes for SAP SuccessFactors

##### 🎟️    Ticketing

- Enhancements to deleted tickets in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Linear
- Support for list.name in remote data for [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Trello

##### 🏆    CRM

- Support for remote fields in [PATCH /Contacts](https://docs.merge.dev/crm/contacts/#contacts_partial_update) for Hubspot

September 6, 2023

https://www.merge.dev/changelog/week-1-september-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, September 2023

# ✨

## Improvements

##### 💰    Accounting

- Support for deleted transactions and transaction lines in [GET/ Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list), [GET/ Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET/ Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list), [GET/ Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET/ Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET/ Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET/ Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Quickbooks Online
- Support for ”status” on [GET/ Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list) for Quickbook Online, Xero, Dynamics, Netsuite, Sage Intacct, and Zoho Books
- Support for ”journal number” on [POST/ Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Quickbook Online, Xero, Microsoft Dynamics Business Central, Netsuite, and Sage Intacct

##### 🤝    ATS

- Enhancements to “New Prospect Created” webhook to notify when a new candidate is created for Greenhouse
- Support for applications in the “Interview Created” webhook for Lever
- Support for [POST/ Candidate](https://docs.merge.dev/ats/candidates/#candidates_create), [POST/ Application](https://docs.merge.dev/ats/applications/#applications_create), and [POST/ Attachment](https://docs.merge.dev/ats/attachments/#attachments_create) for Workday (in beta)

##### 📁    File Storage

- Support for ”permissions” for users who had files/folders shared with them in [GET/ Files](https://docs.merge.dev/filestorage/files/#files_list) and [GET/ Folders](https://docs.merge.dev/filestorage/folders/#folders_list) for Google Drive

##### 🏠    HRIS

- Support for deleted employees in [GET/ Employees](https://docs.merge.dev/hris/employees/#employees_list) for FreshTeam
- Support custom fields with list type in [GET/ Employees](https://docs.merge.dev/hris/employees/#employees_list) for Personio
- Support for ”preferred\_name” on [GET/ Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now, BambooHR, Ceridian Dayforce, ChartHop, Freshteam, Humaans, JumpCloud, Namely, Okta, Paychex, Paylocity, Rippling, SAP SuccessFactors, UKG Pro, UKG Ready, Workday, and Zenefits
- Support for ”employment\_status” for [GET/ Employees](https://docs.merge.dev/hris/employees/#employees_list) for OneLogin, PingOne, Google Workspace, and JumpCloud

##### 🎟️    Ticketing

- Sync enhancement to [GET/ Collections](https://docs.merge.dev/ticketing/collections/#collections_list) for Asana
- Updated /meta to show required fields for [POST/ Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira
- Support for priority in receiving ticket webhook for Zendesk

##### 🏆    CRM

- Sync optimizations for [GET/ Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list), [GET/ Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), and [GET/ Accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for Microsoft Dynamics Sale
- Support for null ”content” field in [GET/ Notes](https://docs.merge.dev/crm/notes/#notes_list) for Salesforce

August 29, 2023

https://www.merge.dev/changelog/week-5-august-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, August 2023

# 🎮

## New Audit Trail and Improved Issues in our Dashboard

We are so excited to continue to enhance our Integrations Management features, giving you full visibility and control over your customers’ integrations.

Audit Trail is now available for Enterprise customers. Merge Dashboard Admins will now have a clear record of security-sensitive actions taken by any member of your Merge org. This feature enhances our existing security features.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ee3561ef5937fc52d1c146_Audit%20Logs%20-%20Admin%20View.webp)

We also have enhanced our Issues feature within our dashboard. Our Issues’ logic has been refined, and is now even more accurate. The improved user interface is easier to understand as it surfaces up relevant issues specific to fields. Relevant issues also now are surfaced at the top of a linked account view.

It is available to everyone so be sure to check it out!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64ee3573a9c3641b58eb105a_Linked%20Account%20-%20Overview%20%2B%20Issue.webp)

# ✨

## Improvements

##### 💰    Accounting

- Sync enhancements to [GET /Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) and [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for QuickBooks Online
- Support for “posting\_status” = “UNPOSTED” for Journals in a "Created" Status in [GET /Journals Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Workday

##### 🤝    ATS

- Support to link [Job Interview Stages](https://docs.merge.dev/ats/job-interview-stages/) to specific [Jobs](https://docs.merge.dev/ats/jobs/) for iCIMS
- Added “interview\_id” as an integration parameter in the [POST /Interviews](https://docs.merge.dev/ats/interviews/#interviews_create) for Greenhouse
- Support for screening questions in [POST /Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) and [GET /candidates/meta/post](https://docs.merge.dev/ats/candidates/#candidates_meta_post_retrieve) via “linked\_account\_params” for Lever

##### 🏠    HRIS

- Support for “departments” in remote data for [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for AzureAD
- Support for updated “groups” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for ADP Workforce Now
- Support for “name” in [GET /Locations](https://docs.merge.dev/hris/locations/#locations_list) for ADP Workforce Now
- Enhancements to “phone\_number” to include country codes in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for SAP SuccessFactors

##### 🎟️    Ticketing

- Sync enhancement to [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) and [GET /Teams](https://docs.merge.dev/ticketing/teams/#teams_list) to support faster syncs for Asana

##### 🏆    CRM

- Support for IsWon, IsClosed, and DefaultProbability fields in remote data in [GET /Stages](https://docs.merge.dev/crm/stages/#stages_list) for Salesforce
- Support for “addresses” in [POST /Leads](https://docs.merge.dev/crm/leads/#leads_create) for Salesforce
- Sync enhancements to [GET /Leads](https://docs.merge.dev/crm/leads/#leads_list) for Salesforce

‍

August 22, 2023

https://www.merge.dev/changelog/week-4-august-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, August 2023

# 🗾

## Field Mapping is now in GA!

Access exactly what data you or your customers need without any limitations. You can now map any data to a field you define, helping you unlock any use case, deliver the extensibility that enterprise customers expect, and create a white-glove onboarding experience to your customers.

Learn more on how to get started in [our docs](https://docs.merge.dev/supplemental-data/field-mappings/overview/)!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54839063401015751af08_ezgif.com-video-to-gif%20(8).gif)

# 🤖

## Search & Ask Merge AI in our Docs and Dashboard

Find what you need in our docs and dashboard now with search! Simply just type in the search bar what you’re looking for and it’ll return the relevant documents in seconds.

We’ve also released “Ask Merge AI” as part of this search. Input any question—from something simple like “What is a linked account?” to something more complex like “Can you write me code using the Python SDK to get open opportunities?”—and you’ll receive the answer you need in seconds.

Check out the demo below to see it in action and try it out for yourself in the [docs](https://docs.merge.dev/)!

Search & Ask Merge AI Feature Overview - YouTube

Merge

202 subscribers

[Search & Ask Merge AI Feature Overview](https://www.youtube.com/watch?v=QLE47mctJe8)

Merge

Search

Info

Shopping

Tap to unmute

If playback doesn't begin shortly, try restarting your device.

You're signed out

Videos you watch may be added to the TV's watch history and influence TV recommendations. To avoid this, cancel and sign in to YouTube on your computer.

CancelConfirm

Share

Include playlist

An error occurred while retrieving sharing information. Please try again later.

Watch later

Share

Copy link

Watch on

0:00

/
•Live

•

[Watch on YouTube](https://www.youtube.com/watch?v=QLE47mctJe8 "Watch on YouTube")

# 🖇️

## Integrations

[Oracle Recruiting Cloud](https://merge.dev/integrations/oracle-fusion-recruiting-cloud) for ATS is now available in limited beta. Please reach out to your Customer Support Manager if you’d like to be a close design partner and provide feedback.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64e54819938311acfbec3042_Oracle%20Recruiting%20Cloud%20Blog.webp)

# ✨

## Improvements

##### 💰    Accounting

- Support for “tracking\_categories” in [POST /Purchase Order](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for NetSuite
- Sync enhancements to [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for NetSuite
- Enhancements with null issue\_date in [GET /Invoices](https://docs.merge.dev/accounting/expenses/#expenses_list) for NetsSuite
- Sync enhancements to [GET /Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list) and [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Quickbooks Online
- Support for deleted data in [GET /Accounts](https://docs.merge.dev/accounting/accounts/#accounts_list), [GET /Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list), [GET /CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list), [GET /Tracking Category](https://docs.merge.dev/accounting/tracking-categories/#tracking_categories_list), [GET /Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [GET /Items](https://docs.merge.dev/accounting/items/#items_list), and [GET /Journal Entry](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Sage Intacct
- Support for deleted line items in [GET /Journal Entries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Workday
- Enhancements to normalization logic for [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/) and [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) for Xero

##### 🤝    ATS

- Support to filter on “created\_after” for [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list), [GET /Applications](https://docs.merge.dev/ats/applications/#applications_list), [GET /Job Interview Stage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list) for Ashby
- Enhancements to applications created in [POST /Candidate](https://docs.merge.dev/ats/candidates/#candidates_create) for JazzHR

##### 🏠    HRIS

- Support for employment\_status and termination\_date in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Officient
- Sync enhancements to [GET /Employee Payroll Runs](https://docs.merge.dev/hris/employee-payroll-runs/#employee_payroll_runs_list) for SAP Success Factor

##### 📁    File Storage

- Enhancements to relinking issues for SharePoint

##### 🎟️    Ticketing

- Support for Linear Teams in [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list), [GET/POST/PATCH Tickets](https://docs.merge.dev/ticketing/tickets/), and webhooks for Linear
- Enhancements to linking flow with a region field for Zoho BugTracker
- Support to link collections to tickets in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Zoho BugTracker
- Support for inactive uses in [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Zoho BugTracker

##### 🏆    CRM

- Sync enhancements to [Account](https://docs.merge.dev/crm/accounts/) Remote Fields for Salesforce
- Enhancements to surface remote IDs and remote data for [Stages](https://docs.merge.dev/crm/stages/) for Salesforce

August 15, 2023

https://www.merge.dev/changelog/week-3-august-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, August 2023

# 👨‍💻

## Migrating to our Advanced SDKs

We’re so excited to be releasing our Advanced SDKs for [Python](https://github.com/merge-api/merge-python-client/), [Java](https://github.com/merge-api/merge-java-client/), [Node](https://github.com/merge-api/merge-node-client/), and [Go](https://github.com/merge-api/merge-go-client/) to speed up your backend integration with Merge!

We encourage you to start migrating to our Advanced SDKs for faster turnaround times on any issue, improved developer interface for request/response classes, access to our latest categories, and a more comprehensive test suite.

The legacy versions (complete category and single category versions) of our Python, Node, Java, and Go SDKs will continue to work but _after February 2024_, we’ll no longer make updates or bug fixes to the deprecated SDKs.

Please check out our [Help Center](https://help.merge.dev/en/articles/7992820-using-merge-sdks) and [docs](https://docs.merge.dev/sdk/) to learn more and get started with comprehensive migration guides.

# ✨

## Improvements

- Enhancements to Common Model docs by adding full endpoint URL and copy buttons for both US and EU

##### 💰    Accounting

- Support for “posting\_status”=“POSTED” in [POST /Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_create) for Xero
- Support for ”currency” in [GET /Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list), [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list), [GET /Expenses](https://docs.merge.dev/accounting/expenses/) and [GET /Purchase](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list) Orders for Netsuite
- Support for ”currency” in [GET /Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET /Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET /Credit Notes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET /Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) and [GET /Expenses](https://docs.merge.dev/accounting/expenses/) for Sage Intacct
- Support for ”currency” in [GET /Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Workday

##### 🤝    ATS

- Sync enhancements for [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for iCIMs

##### 🏠    HRIS

- Support for ”start\_date” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for 7Shifts
- Support for ”work\_location” and ”date\_of\_birth” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Deel
- Support for deleted employees in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Officient
- Support for custom fields in [GET /Employees](http://employeehttps/) for Factorial

##### 🎟️    Ticketing

- Normalized “delivered” to “closed” for ”status” in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Aha!
- Sync enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list), [GET /Collections](https://docs.merge.dev/ticketing/collections/#collections_list), [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list), [GET /Attachments](https://docs.merge.dev/ticketing/attachments/#attachments_list) and [GET /Tags](https://docs.merge.dev/ticketing/tags/#tags_list) for Asana
- Sync enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Dixa
- Support for ”priority”, ”description”, and ”contact” in [PATCH /Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Freshdesk
- Sync enhancements to [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list) and [GET /Attachments](https://docs.merge.dev/ticketing/attachments/) for Zendesk

##### 🏆    CRM

- Enhancements to error messaging for [POST /Contacts](https://docs.merge.dev/crm/contacts/#contacts_create) for Salesforce
- Sync enhancements for remote fields in [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list) for Salesforce

August 8, 2023

https://www.merge.dev/changelog/week-2-august-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, August 2023

# 🌊

## Async Passthrough is available in open beta

[Async passthrough](https://docs.merge.dev/supplemental-data/passthrough/async-passthrough/) allows you to retrieve the response at a later time. We built this feature since third-party response times differ and can cause delays for when calling passthrough requests.

With async passthrough you won't have to wait for a response before calling other requests or endpoints! We’ll also notify you through a webhook when your response is ready.

Learn more [here](https://help.merge.dev/en/articles/8032634-async-passthrough#h_a5c8d26dc3).

# 👨‍👨‍👦

## New HRIS Common Models

We are super excited to announce two new HRIS common models to expand our benefits capabilities: [Employer Benefits](https://docs.merge.dev/hris/employer-benefits/) and [Dependents](https://docs.merge.dev/hris/dependents/).

With these new Common Models, customers can now unlock use cases such as determining the count of an employees’ dependents and the nature of their relationship and retrieving information on the benefit plans offered by a company.

Take a look at the docs and let us know if you have any questions or feedback! We’ll be planning to expand integration coverage for these Common Models.

# ✨

## Improvements

- Enhancements to Logs filtering UX in the Dashboard
- Enhancements to sync status notifying when Merge has hit a 3rd party rate limit and is waiting to sync
- Enhancements to sync status card on Linked Account view; we only surface the most relevant statuses at the top

##### 💰    Accounting

- Support for deleted data for [Account](https://docs.merge.dev/accounting/accounts/), [Company Info](https://docs.merge.dev/accounting/company-info/), [Contacts](https://docs.merge.dev/accounting/contacts/), [Credit Notes](https://docs.merge.dev/accounting/credit-notes/), [Expenses](https://docs.merge.dev/accounting/expenses/), [Invoices](https://docs.merge.dev/accounting/invoices/), [Items](https://docs.merge.dev/accounting/items/), [Journal Entries](https://docs.merge.dev/accounting/journal-entries/), [Payments](https://docs.merge.dev/accounting/payments/), [Purchase Orders](https://docs.merge.dev/accounting/purchase-orders/), [Tracking Categories](https://docs.merge.dev/accounting/tracking-categories/), [Transactions](https://docs.merge.dev/accounting/transactions/), [Vendor Credits](https://docs.merge.dev/accounting/vendor-credits/) for Netsuite
- Support for deleted report items in [GET /IncomeStatements](https://docs.merge.dev/accounting/income-statements/#income_statements_list) for Netsuite
- Support for [GET /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for Netsuite
- Support for Credit Card Payment type in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for QuickBooks Online
- Support for “memo” in [POST /Expenses](https://docs.merge.dev/accounting/expenses/#expenses_create) for QuickBooks Online
- Support for Transfer type in [GET /Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for Xero
- Sync enhancements for [GET /JournalEntries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Xero

##### 🤝    ATS

- Support for webhooks for Candidate stage change, Job deleted, Offer created, Offer updated, and Offer deleted events for Ashby
- Support for deleted “departments”, “recruiters”, and “hiring\_mangers” in [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Greenhouse
- Updated authentication to standardize linking accounts across regions for JobAdders

##### 🏠    HRIS

- Support for “employment\_status” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for 7Shifts
- Support for “company” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Deel
- Sync enhancement for [GET /Employments](https://docs.merge.dev/hris/employments/#employments_list) and [GET/Employees](https://docs.merge.dev/hris/employees/#employees_list) for UKG Pro

##### 🎟️    Ticketing

- Sync enhancements to [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list) for Intercom
- Support for [GET /Tags](https://docs.merge.dev/ticketing/tags/#tags_list) for ServiceNow
- Support to add new tags in [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ServiceNow
- Support for deleted users in [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Zendesk
- Enhancements to sync times for [GET /Attachments](https://docs.merge.dev/ticketing/attachments/#attachments_list), [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list), [GET /Contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list), and [GET /Users](https://docs.merge.dev/ticketing/users/#users_list) for Zendesk

##### 🏆    CRM

- Enhancements to surface remote IDs and remote data for [Stages](https://docs.merge.dev/crm/stages/) for HubSpot
- Support for [POST /Notes](https://docs.merge.dev/crm/notes/#notes_create) for Pipedrive
- Support for deleted data in [GET /Accounts](https://docs.merge.dev/crm/accounts/#accounts_list), [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list), [GET /Leads](https://docs.merge.dev/crm/leads/#leads_list), [GET /Notes](https://docs.merge.dev/crm/notes/#notes_list), [GET /Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) and [GET /Tasks](https://docs.merge.dev/crm/tasks/#tasks_list) for Salesforce
- Sync enhancements to [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) and [GET /EngagementType](https://docs.merge.dev/crm/engagement-types/#engagement_types_list) for Zoho CRM

August 1, 2023

https://www.merge.dev/changelog/week-1-august-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, August 2023

# ✨

## Improvements

- Enhancements to Merge Link loading time

##### 💰    Accounting

- Enhancements to Purchase Orders objects in [POST /PurchaseOrder](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_create) for NetSuite
- Support for deleted report items in [GET /BalanceSheet](https://docs.merge.dev/accounting/balance-sheets/#balance_sheets_list), [GET /CashFlowStatements](https://docs.merge.dev/accounting/cash-flow-statements/#cash_flow_statements_list), and [GET /IncomeStatement](https://docs.merge.dev/accounting/income-statements/#income_statements_list) for QuickBooks Online and Xero

##### 🤝    ATS

- Enhancements with null candidates in [GET /Candidates](https://docs.merge.dev/ats/candidates/#candidates_list) for Greenhouse
- Support for automated webhooks for Application created, Candidate stage change, Candidate hired, Candidate deleted, Interview created, Interview updated, and Interview deleted events for Lever
- Support for “applied\_at” in [GET /Application](https://docs.merge.dev/ats/applications/#applications_list) for SAP SuccessFactors
- Support for “status” on [GET /Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for UKG Pro Recruiting

##### 🏠    HRIS

- Support for “&” character in “name” in [GET /Groups](https://docs.merge.dev/hris/groups/#groups_list) for Ceridian
- Enhancements to  “work\_location” in [GET /Employees](https://docs.merge.dev/hris/employees/#employees_list) for Ceridian
- Enhancements to date format in [GET /Employee](https://docs.merge.dev/hris/employees/#employees_list), [GET /Employment](https://docs.merge.dev/hris/employments/#employments_list), and [GET /Location](https://docs.merge.dev/hris/locations/#locations_list) for Ceridian
- Enhancements to authentication issues when linking account for Officient
- Update logic to map “type” as Department in [GET /Groups](https://docs.merge.dev/hris/groups/) for TriNet
- Added sync enhancements for GET requests for TriNet

##### 🎟️    Ticketing

- Support for "remote\_created\_after" filter for [GET /Attachments](https://docs.merge.dev/ticketing/attachments/#attachments_list) and [GET /Comments](https://docs.merge.dev/ticketing/comments/#comments_list)
- Added error messaging for tag issues in [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Asana
- Support to create tickets with a new “contact” instantly in [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Freshdesk
- Added stricter validation logic in Merge Link for Jira
- Support for [PATCH /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ServiceNow
- Support for “tags” in [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for ServiceNow
- Enhancements to “collection” response in [POST /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Teamwork
- Support for automated webhooks for Deleted [Collection](https://docs.merge.dev/ticketing/collections/) events for Wrike
- Support for “completed\_at” in [GET /Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) for Teamwork, Wrike, Hive, Basecamp

##### 🏆    CRM

- Added syncing enhancement in [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) and [GET /EngagementTypes](https://docs.merge.dev/crm/engagement-types/#engagement_types_list) for Keap
- Added support for “contacts” in [GET /Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Keap
- Support for deleted data in [GET /Accounts](https://docs.merge.dev/crm/accounts/#accounts_list), [GET /Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), and [GET /Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Hubspot
- Support for “engagements” with no associated “contacts” in [POST /Engagements](https://docs.merge.dev/crm/engagements/#engagements_create) for Salesforce
- Support for remote fields in [PATCH /Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Salesforce
- Enhancements to [POST /Engagements](https://docs.merge.dev/crm/engagements/#engagements_create) for Salesforce
- Support for “&”, “<”, “>” characters in “subject” and “content” in [POST /Task](https://docs.merge.dev/crm/tasks/#tasks_create)

July 25, 2023

https://www.merge.dev/changelog/week-4-july-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, July 2023

# **📁**

## File Storage is now in general availability!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6410d75f475ba344a690149e_File%20Storage%20Integrations.png)

Our 7th Unified API category, File Storage, is now widely available.

File Storage currently supports 5 integrations: Google Drive, Dropbox, Box, SharePoint, and OneDrive.

Access real-time, normalized data for files, folders, drives, to power different use cases such as automatically uploading and downloading documents or searching for a specific file!

Some major enhancements to File Storage, thanks to feedback from our beta customers, are:

- File Picker: An out-of-the-box, UI-friendly feature that allows your customers to browse and select files and folders from their file storage platform, regardless of which one they use! (Note that this feature is still in beta, but if you would like to use it for your use case, please reach out to your EM or support@merge.dev.)
- Real-time files, folders, and drives with supported third-party webhooks.
- Support of files and folder permissions data using newly added Common Models: Users and Groups

Try it out now using our developer docs [here](https://docs.merge.dev/filestorage/overview/)! If you’re interested in discussing your specific use case and how Merge can support it, you can talk to someone [here](https://merge.dev/get-in-touch?utm_btn=dr-page-changelog).

# **✨**

## Improvements

- Enhancements to Field Mapping during end user relinking flow
- Enhancements to UX for Logs in Merge Dashboard
- Enhancements to [Rippling integration Docs page](https://docs.merge.dev/integrations/hris/rippling/provider-interactions/) ‍
- Added back “ [View all Integrations](https://docs.merge.dev/integrations/hris/overview/)” page to the “Integrations” section in Docs

##### 💰    Accounting

- Support for document number in remote data for [GET/PurchaseOrder](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list) for NetSuite
- Support for [GET/Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list) for NetSuite
- Support for “tracking\_categories” in [POST/Invoices](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSutie
- Enhancements to remote\_data in [GET/Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for NetSuite
- Enhancements to remove deleted “tracking\_categories” from appearing in [GET/JournalEntries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) for Quickbooks Online
- Support for multi-base currency in [GET/CompanyInfo](https://docs.merge.dev/accounting/company-info/#company_info_list) for Sage Intacct

##### 🤝    ATS

- Support for [GET/Jobs](https://docs.merge.dev/ats/jobs/#jobs_list), [GET/JobInterviewStage](https://docs.merge.dev/ats/job-interview-stages/#job_interview_stages_list), and [GET/Applications](https://docs.merge.dev/ats/applications/#applications_list) for Infinite BrassRing
- Added error handling for null fields in [POST/Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Clockwork
- Enhancements to [POST/Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) syncs for Harbour ATS

##### 📁    File Storage

- Support to select strictly read-only permission for SharePoint
- Enhancements to sync frequency to improve efficiency for all File Storage integrations to capture real-time updates
- Support for query parameters including "drive\_id" for [GET/Files](https://docs.merge.dev/filestorage/files/#files_list) and is\_me=true for [GET/Users](https://docs.merge.dev/filestorage/users/#users_list)

##### 🏠    HRIS

- Support to pull time off requests in the future for [GET/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for Ceredian
- Enhancements to “employment\_type” in [GET/Employments](https://docs.merge.dev/hris/employments/#employments_list) for HiBob
- Updated logic to show “pay\_rate” based on “pay\_period” in [GET/Employees](https://docs.merge.dev/hris/employees/#employees_list) for Namely
- Added error handling for null “job\_title in [GET/Employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro
- Enhancements to sync times for [GET/Employments](https://docs.merge.dev/hris/employments/#employments_list) for UKG Pro

##### 🎟️    Ticketing

- Added sync optimizations for webhooks for [Tickets](https://docs.merge.dev/ticketing/tickets/) for Jira
- Enhancements to show all records in [GET/Accounts](https://docs.merge.dev/ticketing/accounts/#accounts_list), [GET/Contacts](https://docs.merge.dev/ticketing/contacts/#contacts_list), [GET/Comments](https://docs.merge.dev/ticketing/comments/#comments_list), [GET/Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [GET/Users](https://docs.merge.dev/ticketing/users/#users_list) for Salesforce Service Cloud

##### 🏆    CRM

- Support for remote fields in for [PATCH/Accounts](https://docs.merge.dev/crm/accounts/#accounts_partial_update), [PATCH/Contacts](https://docs.merge.dev/crm/contacts/#contacts_partial_update), [PATCH/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Pipedrive
- Added sync optimizations for [GET/Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), [GET/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list), [GET/Accounts](https://docs.merge.dev/crm/accounts/#accounts_list), [GET/Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) forZoho CRM

# **👨‍💻**

## **SDK Updates**

- Updated Typescript SDK to [v3.2.2](https://github.com/merge-api/merge-sdk-typescript) ‍
- Updated Java HRIS SDK to [v1.4.2](https://github.com/merge-api/merge-hris-java)

‍

July 18, 2023

https://www.merge.dev/changelog/week-3-july-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, July 2023

# 🖇️

## Integrations

Sage Intacct integration is now available in beta. If you’re interested, please reach out to your Customer Support Manager or support@merge.dev to have someone turn it on for you to access.

Take a look at our initial support for Models and Fields in [our docs](https://docs.merge.dev/integrations/accounting/sage-intacct/provider-interactions/).

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64b70f29a78df027b66f8bd7_Sage%20Intacct%20Blog.webp)

# ✨

## Improvements

- Enhancements to Get Started, including improved descriptions for Test and Production Linked Accounts
- Support to test every category endpoint under the [Try Unified API](https://app.merge.dev/get-started/send-api-request) page
- Added new Magic Link intro pop-up information page

##### 💰    Accounting

- Support for deleted tracking categories from transactions in [GET/Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET/JournalEntries](https://docs.merge.dev/accounting/journal-entries/), [GET/PurchaseOrders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET/Transactions](https://docs.merge.dev/accounting/transactions/), and [GET/VendorCredits](https://docs.merge.dev/accounting/vendor-credits/) for Netsuite
- Support for deleted tracking categories from transactions in [GET/CreditNote](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET/Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [GET/Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET/JournalEntries](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list), [GET/Payments](https://docs.merge.dev/accounting/payments/#payments_list), [GET/PurchaseOrders](https://docs.merge.dev/accounting/purchase-orders/#purchase_orders_list), [GET/Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list), and [GET/VendorCredits](https://docs.merge.dev/accounting/vendor-credits/) for QuickBooks Online
- Enhancements to show modified expenses in the correct month in Income Statement for Quickbooks Online
- Support for remote data for [GET/Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list), [GET/CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET/Expenses](https://docs.merge.dev/accounting/expenses/#expenses_list), [GET/Invoices](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET/Items](https://docs.merge.dev/accounting/items/#items_list) and [GET/VendorCredits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Sage Intacct
- Enhancements to missing data fields and logic for [GET/Contact](https://docs.merge.dev/accounting/contacts/#contacts_list), [GET/CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list), [GET/Expense](https://docs.merge.dev/accounting/expenses/#expenses_list), [GET/Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list), and [GET/VendorCredits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Sage Intacct
- Support for deleted tracking categories from transactions in [GET/CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) and [GET/VendorCredits](https://docs.merge.dev/accounting/vendor-credits/#vendor_credits_list) for Xero

##### 🤝    ATS

- Sync optimizations for [GET/Candidates](https://docs.merge.dev/ats/candidates/#candidates_list), [GET/Applications](https://docs.merge.dev/ats/applications/#applications_list), and [GET/Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for iCIMS
- Enhancements to fetching resumes for [POST/Attachments](https://docs.merge.dev/ats/attachments/#attachments_create) for iCIMS
- Enhancements to pulling required fields in [POST/Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for Fountain

##### 🏠    HRIS

- Enhancements to null values for ”effective\_date” in [GET/ Employment](https://docs.merge.dev/hris/employments/#employments_list) for ADP Workforce Now
- Enhancements to syncing logic for [GET/Groups](https://docs.merge.dev/hris/groups/#groups_list) to fix timeout issue for Ceridian Dayforce
- Sync optimizations for [GET/Employees](https://docs.merge.dev/hris/employees/) for Deel
- Enhancements to linking flow to remove “Organization API Key” field for end user authentication for Deel
- Support for [GET/PayGroups](https://docs.merge.dev/hris/pay-groups/#pay_groups_list) for HRAlliance

##### 🎟️    Ticketing

- Support for ”priority” field in [POST/Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Jira

##### 🏆    CRM

- Sync optimizations for [GET/Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), [GET/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list), [GET/Accounts](https://docs.merge.dev/crm/accounts/), [GET/Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Salesforce
- Sync optimizations for [GET/Contacts](https://docs.merge.dev/crm/contacts/#contacts_list), [GET/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list), [GET/Accounts](https://docs.merge.dev/crm/accounts/), [GET/Engagements](https://docs.merge.dev/crm/engagements/#engagements_list) for Zoho CRM

##### 📁    File Storage

- Enhancements to webhooks to support file permission changes for Box
- Enhancements to webhooks to support deleted files for Google Drive
- Support for webhooks to notify if File or Folder was modified or deleted for OneDrive
- Support for webhooks to notify if File or Folder was modified or deleted for SharePoint
- Support for ”User.is\_me” in [GET/ Users](https://docs.merge.dev/filestorage/users/#users_retrieve) for Box, Dropbox, Google Drive, OneDrive, and SharePoint to identify if a user linked their own account

# 🧑‍💻

## SDK Updates

• Updated Python SDK to [v2.3.0](https://pypi.org/project/MergePythonSDK/)

July 11, 2023

https://www.merge.dev/changelog/week-2-july-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, July 2023

# ✨

## Improvements

- Enhancement to both UI and content in Docs and Dashboard

##### 💰    Accounting

- Enhancements to created objects for [GET/Items](https://docs.merge.dev/accounting/items/#items_list) for Clear Books
- Enhancements to specify ”tracking category” for [GET/PurchaseOrder](https://docs.merge.dev/accounting/purchase-orders/) for NetSuite
- Support for shell objects being created in [GET/CompanyInfo](https://docs.merge.dev/accounting/company-info/) for NetSuite
- Enhancements to [GET/TrackingCategories’s](https://docs.merge.dev/accounting/tracking-categories/) logic to improve data accuracy for Xero
- Enhancements to “exchange\_rate” for transaction objects for Xero
- Enhancements to [GET/Invoice](https://docs.merge.dev/accounting/invoices/#invoices_list), [GET/Expense](https://docs.merge.dev/accounting/expenses/#expenses_list), and [GET/CreditNotes](https://docs.merge.dev/accounting/credit-notes/#credit_notes_list) syncs for Xero
- Enhancements to pull pull correct dates for [GET/BalanceSheets](https://docs.merge.dev/accounting/balance-sheets/)

##### 🤝    ATS

- Enhancements to [POST/Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) for iCIMs
- Added sync optimizations for [GET/Interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Lever
- Support for [GET/Offers](https://docs.merge.dev/ats/offers/) for Jobvite

##### 🏠    HRIS

- Enhancements to [GET/Groups](https://docs.merge.dev/hris/groups/#groups_list) for ADP Workforce
- Support for “employment\_status” and “termination\_date” under [GET/Employees](https://docs.merge.dev/hris/employees/) for Azure Active Directory
- Support to pull additional custom fields with Field Mappings feature for [GET/Employees](https://docs.merge.dev/hris/employees/) for HiBob
- Support to pull MFA information in “remote\_data” for OneLogin
- Added error check to access MFA information in “remote\_data” for OneLogin
- Enhancements to [GET/PayrollRun](https://docs.merge.dev/hris/payroll-runs/#payroll_runs_list) syncs for Paychex
- Added ability to pull time off requests in the future for [GET/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for SageHR
- Enhancements to [GET/Employees](https://docs.merge.dev/hris/employees/) syncs for UKG Ready
- Enhancements to “status” under [GET/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for Workday

##### 🎟️    Ticketing

- Support for [GET :id/download](https://docs.merge.dev/ticketing/attachments/#attachments_download_retrieve) for !Aha, Asana, Bitbucket, Clickup, Freshdesk, Freshservice, Jira, Linear, Teamwork, Trello, ServiceNow, Wrike, and Zendesk
- Support for [GET/Attachment](https://docs.merge.dev/ticketing/attachments/#attachments_list) for !Aha and Freshservice
- Support for Remote Fields for [GET/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_list) and [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Asana
- Enhancements to refresh logic for Basecamp
- Added optimizations to handle rate limiting for Basecamp
- Support for “body” field under [GET/Comment](https://docs.merge.dev/ticketing/comments/#comments_list) for Basecamp and Teamwork

##### 🏆    CRM

- Enhancements to [GET/Tasks](https://docs.merge.dev/crm/tasks/#tasks_list) for Close
- Enhancements to [GET/Stages](https://docs.merge.dev/crm/stages/#stages_list) for Close
- Added optimizations for [GET/Contacts](https://docs.merge.dev/crm/contacts/) for Hubspot
- Support for “addresses” under [GET/Contacts](https://docs.merge.dev/crm/contacts/) for Hubspot
- Support for “addresses” under [GET/Accounts](https://docs.merge.dev/crm/accounts/) for Hubspot
- Enhancements to “employee\_count” syncs under [GET/Accounts](https://docs.merge.dev/crm/accounts/) for Hubspot
- Enhancements to “remote\_data” for Hubspot
- Enhancements to Remote Fields for Hubspot
- Support for “email” and “phone” under [POST/Contacts](https://docs.merge.dev/crm/contacts/#contacts_create) for Pipedrive
- Enhancements to [POST/Notes](https://docs.merge.dev/crm/notes/#notes_create) to validate permissions for Salesforce
- Enhancements to “remote\_fields” for [POST/Opportunity](https://docs.merge.dev/crm/opportunities/#opportunities_create) for Salesforce
- Support for “opportunity” under [POST/Tasks](https://docs.merge.dev/crm/tasks/#tasks_create) for Salesforce

##### 📁    File Storage

- Support to connect and authenticate through partner credentials for Google Drive

June 27, 2023

https://www.merge.dev/changelog/week-5-june-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 5, June 2023

# 🎮

## Announcing Integrations Management

The [Merge Dashboard](https://app.merge.dev/) has gone through major enhancements to provide full visibility and control into each of your linked accounts.

Maintaining integrations is much more time consuming than the initial build, which is why we're excited about announcing our comprehensive suite of tools: Integrations Management.

Enhancements that we've made in the Merge Dashboard include:

- Viewing an accurate, live status of your customers' integration data syncs
- Searching comprehensive logs for visibility into every single API request at the linked account level
- Getting proactive alerts of any customer set-up issues such as outdated API keys, both in the dashboard and via API
- Controlling and customizing what data is shared, respecting your customers’ privacy

We have more improvements coming soon so keep an eye out! If you're interested in learning how to better use the Merge Dashboard to mange your integrations, [sign up for our webinar](https://www.linkedin.com/events/7078961692390395904/comments/) on July 11,2023 at 10am PT / 1pm ET.

# 🖇️

## Integration Update

Please note that BizMerlinHR has been rebranded as [ClayHR](https://merge.dev/integrations/clayhr) under the HRIS Unified API.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/649b4a50d7417fdf2e3a720e_ClayHR%20Blog.webp)

# ✨

## Improvements

- Support to pull Transfer data in [GET/Transactions](https://docs.merge.dev/accounting/transactions/#transactions_list) for QuickBooks Online
- Support for ”contact” field on [GET/JournalEntry](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) lines for NetSuite
- Enhancements to accounts not linking for multiple environments for Microsoft Dynamics
- Enhancements to [POST/Activity](https://docs.merge.dev/ats/activities/#activities_create) to populate “remote\_id” for Greenhouse
- Enhancements to “remote\_data” populating for Jobvite
- Enhancements to [JobInterviewStage](https://docs.merge.dev/ats/job-interview-stages/) for Fountain
- Enhancements to refresh tokens for Lever
- Support for [PATCH/Candidate](https://docs.merge.dev/ats/candidates/#candidates_partial_update) support for JobAdder
- Support to filter out deleted jobs in [GET/Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for SAP SuccessFactors
- Enhancements to “pay\_rate” syncing on [GET/Employment](https://docs.merge.dev/hris/employments/#employments_list) for Deel
- Enhancements to “pay\_rate” on [GET/Employment](https://docs.merge.dev/hris/employments/#employments_list) for Ceridian
- Enhancements to syncing payroll runs for Paychex
- Added rate limit optimizations to BambooHR, UKG Pro, and UKG Ready
- Added optimizations for larger accounts for Workday
- Enhancements to [GET/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) status for Workday
- Enhancements to validation logic to account for end users not granting access to compensation for UKG Pro
- Support for custom fields in ”remote\_data” for Freshteam
- Enhancements to [GET/Employees](https://docs.merge.dev/hris/employees/) syncs for Trinet
- Added dedupe logic for employees for Payfit
- Support to pull MFA data for Employees for OneLogin
- Enhancements to “remote\_data” for [GET/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_list) for BambooHR
- Support to pull profile pictures for employees for CharlieHR
- Enhancements to [GET/Users](https://docs.merge.dev/ticketing/users/#users_list) for Teamwork
- Enhancements to Ticket Created webhook for Linear
- Enhancements to automatic webhooks for Github Issues
- Support for “priority” field to [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) and [PATCH/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Linear
- Support for 3rd party Deleted Ticket detection for Trello, Teamwork, Zendesk, Front, and Re:Amaze
- Enhancements to File Picker (in beta) to optimize speed for Box, Google Drive, OneDrive, SharePoint, and Dropbox

# 👨‍💻

## SDK Updates

- Updated PHP ATS SDK to [v1.0.2](https://github.com/merge-api/merge-ats-php)
- Updated PHP HRIS SDK to [v2.0.1](https://github.com/merge-api/merge-hris-php)
- Updated PHP Ticketing SDK to [v1.0.1](https://github.com/merge-api/merge-ticketing-php)

June 21, 2023

https://www.merge.dev/changelog/week-4-june-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, June 2023

# ✨

## Improvements

- [Supported Fields page](https://docs.merge.dev/integrations/hris/supported-fields/) is now the default page under “Integrations” in docs
- Enhancements to [Common Model docs](https://docs.merge.dev/hris/overview/) to remove “object” header in left-hand nav
- Addition of [Field Mapping](https://docs.merge.dev/guides/field-mappings/overview/) to Supplemental Data section in Docs
- Enhancements to [POST/Invoice](https://docs.merge.dev/accounting/invoices/#invoices_create) for NetSuite
- Enhancements to [GET/Addresses](https://docs.merge.dev/accounting/addresses/#addresses_retrieve) for NetSuite
- Enhancements to top level ”tracking\_category” relation for [GET/Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list)
- Support for [PATCH/Candidate](https://docs.merge.dev/ats/candidates/#candidates_partial_update) for Ashby, Greenhouse, Lever, and SmartRecruiter (in beta)
- Support for [POST/Interview](https://docs.merge.dev/ats/interviews/#interviews_create) for Lever and Recruitee
- Enhancements with webhooks for Greenhouse
- Enhancements to authentication for Lever
- Enhancements to permissions for [GET/Attachments](https://docs.merge.dev/ats/attachments/#attachments_list) for SmartRecruiters
- Added optimizations to support large syncs for Teamtailor
- Added ”opportunity” relation to [GET/Task](https://docs.merge.dev/crm/tasks/#tasks_list) for Hubspot and Salesforce
- Enhancements to [GET/Accounts](https://docs.merge.dev/crm/accounts/#accounts_list) for greater efficiency for Hubspot and Salesforce
- Increased highest sync frequency settings for all models for Zoho CRM
- Upgraded API version to pull updated data for Zoho CRM
- Support for “converted\_account”, “converted\_date”, “converted\_contact”, “email\_addresses”, “phone\_numbers”, and “title” to [GET/Leads](https://docs.merge.dev/crm/leads/#leads_list)
- Added support for ”opportunity” and “account” on [GET/Notes](https://docs.merge.dev/crm/notes/#notes_list) for Zoho CRM
- Enhancements to  [GET/Teams](https://docs.merge.dev/hris/teams/#teams_list) for ADP Workforce Now
- Enhancements to input parameters for [POST/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_create) for Ceridian Dayforce
- Enhancements to remote data for [GET/Employees](https://docs.merge.dev/hris/employees/#employees_list) for Insperity
- Enhancements to [TimeOff](https://docs.merge.dev/hris/time-off/) status field for Justworks
- Added optimizations to support long sync for Okta
- Increased highest sync frequency settings for UKG Ready
- Support to retrieve ”ticket\_type” enum choices to [POST/ticket/meta](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Bitbucket, Freshdesk, Freshservice, Height, and Zendesk
- Support for deleted tickets for Freshdesk, Front, Re:amaze, Teamwork, Jira, ClickUp, Linear, Trello, and Zendesk
- Added automatic webhook support for deleted tickets for Clickup, Freshdesk, Jira, and Linear
- Enhancements to OAuth for Box
- Enhancements to webhook setup for Box
- Updated ”file\_thumbnail\_url” to make static for OneDrive and Sharepoint

# 🧑‍💻

## SDK Updates

- Updated C# Accounting SDKs to [v1.1.1](https://github.com/merge-api/merge-accounting-csharp-net)
- Updated C# HRIS SDKs to [v2.1.0](https://github.com/merge-api/merge-hris-csharp-net)
- Updated C# CRM SDKs to [v1.0.1](https://github.com/merge-api/merge-crm-csharp-net)
- Updated Go Accounting SDKs to [v1.3.0](https://github.com/merge-api/merge-accounting-go/blob/main/README.md)
- Updated Go CRM SDKs to [v1.3.0](https://github.com/merge-api/merge-crm-go/blob/main/README.md)
- Updated Go Ticketing SDKs to [v1.3.0](https://github.com/merge-api/merge-ticketing-go/blob/main/README.md)
- Updated Go HRIS SDKs to [v1.3.0](https://github.com/merge-api/merge-hris-go/blob/main/README.md)
- Updated Typescript SDK to [v3.2.0](https://github.com/merge-api/merge-sdk-typescript)

June 14, 2023

https://www.merge.dev/changelog/week-3-june-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, June 2023

# **✨**

## Improvements

- Enhancements to [GET/Locations](https://docs.merge.dev/hris/locations/#locations_list) work “location\_type” for Workday
- Enhancements to [GET/TimeOffBalance](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) type field for BambooHR
- Enhancements to [GET/TimeOffBalance](https://docs.merge.dev/hris/time-off-balances/#time_off_balances_list) syncing for BambooHR
- Enhancements to [GET/Employments](https://docs.merge.dev/hris/employments/) remote data for ADP Workforce Now
- Added additional coverage to ADP Workforce Now
- Enhancements to [GET/Employee](https://docs.merge.dev/hris/employees/#employees_list) “employment\_status” for pending employees for Justworks
- Support for work location “name” for [GET/Locations](https://docs.merge.dev/hris/locations/#locations_list) for ADP Workforce Now
- Enhancements to error handling for permissions for SharePoint
- Enhancements to error handling for permissions issues for Azure Active Directory
- Enhancements to [GET/Employees](https://docs.merge.dev/hris/employees/) for Payfit
- Enhancements to [GET/Groups](https://docs.merge.dev/hris/groups/#groups_list) null data for UKG Ready
- Enhancements to [POST/TimeOff](https://docs.merge.dev/hris/time-off/#time_off_create) type mappings for BambooHR
- Support for [GET/Employee](https://docs.merge.dev/hris/employees/#employees_list) custom fields for Freshteam
- Enhancements to [GET/Employee](https://docs.merge.dev/hris/employees/#employees_list) “pay\_period” field for hourly employees for Paylocity
- Support for [POST/Application](https://docs.merge.dev/ats/applications/#applications_create) for Harbour ATS
- Support for [POST/Application](https://docs.merge.dev/ats/applications/#applications_create) for Comeet
- Enhancements to webhooks authentication for Greenhouse
- Enhancements to [GET/Journals](https://docs.merge.dev/accounting/journal-entries/) to pull ”journal\_lines”, “currency\_rate\_type” and support retained earnings and translation adjustment journals for Workday Financial
- Enhancements to [POST/Contacts](https://docs.merge.dev/accounting/contacts/#contacts_create) for Netsuite
- Support for [GET/Journals](https://docs.merge.dev/accounting/journal-entries/#journal_entries_list) “posting\_status” enum mapping for Workday Financial
- Enhancements to normalization of [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) to return more fields in response for Aha!
- Enhancements to /meta endpoint for required fields for Aha!
- Support for [GET/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_list) ”completed\_at” field for Azure DevOps, Trello, Basecamp, FreshService, and Jira Service Management
- Enhancements to [GET/Tickets](https://docs.merge.dev/ticketing/tickets/#tickets_list) pagination for Shortcut
- Support for [GET/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_list) ”created\_at” and ”updated\_at” for Jira Service Management
- Support for [PATCH/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) for Rally
- Enhancements to [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) error messaging for Wrike
- Enhancements to [POST/Leads](https://docs.merge.dev/crm/leads/) for Salesforce
- Added optimizations to improve performance for larger accounts to sync [GET/Accounts](https://docs.merge.dev/crm/accounts/#accounts_list), [GET/Contacts](https://docs.merge.dev/crm/contacts/#contacts_list) and [GET/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_list) for Zoho CRM
- Enhancements to OAuth linking for Pipedrive
- Support for converted\_account, converted\_contact, converted\_date, email\_addresses, phone\_numbers, title for [GET/Leads](https://docs.merge.dev/crm/leads/#leads_list) for Zoho CRM
- Support for passing in reserved XML characters for [POST](https://docs.merge.dev/crm/opportunities/#opportunities_create) and [PATCH/Opportunities](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update) for Salesforce
- Enhancements to security to ”file\_thumbnail\_url” fields across all File Storage integrations
- Support for receiving webhooks for Box
- Enhancements to webhooks for Google Drive
- Support for [user](https://docs.merge.dev/filestorage/users/) and permissions model for Google Drive

# **👨‍💻**

## SDK Updates

- Updated Ruby HRIS SDK to [v3.2.0](https://github.com/merge-api/merge-hris-ruby)
- Updated Ruby ATS SDK to [v3.0.1](https://github.com/merge-api/merge-ats-ruby)
- Updated Ruby Ticketing SDK to [v1.0.8](https://github.com/merge-api/merge-accounting-ruby)
- Updated Ruby Accounting SDK to [v1.0.4](https://github.com/merge-api/merge-accounting-ruby)

June 6, 2023

https://www.merge.dev/changelog/week-2-june-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, June 2023

# 🤖

## Meet Blueprint

We are thrilled to introduce our new AI-powered tool, Blueprint. Now available in beta, Blueprint uses AI to read API documentation and automatically starts building an integration to one of Merge’s seven Unified APIs.

Anyone can contribute to Merge’s Unified APIs, and accelerate the development of integrations offered through Merge’s platform.

[Try it out now!](https://www.merge.dev/campaigns/blueprint)

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc0b9c5336d6af08c29187_647f8dca9cc2e3e446d56e57_Screenshot%25202023-06-02%2520at%252011.27.07%2520AM.webp)

# **🖇️**

## New Integration

We’re excited to expand our Ticketing Unified API with the addition of [Rally](https://merge.dev/integrations/rally) which is now available in beta!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/66fc0b9c5336d6af08c29140_647f8dd4f5fcc193a4402e7d_Rally%2520Blog.webp)

# **✨**

## Improvements

- Support for “start\_date” and “end\_date” under [Benefits](https://docs.merge.dev/hris/benefits/) for BambooHR, ADP, Paylocity, UKG Ready, and UKG Pro
- Enhancements to runtime optimizations for Okta
- Enhancements to accounts linking for Factorial
- Support for “start\_date”, “employment\_status” and compensation details under [Employments](https://docs.merge.dev/hris/employments/) for Deel
- Enhancements to linking [Employees](https://docs.merge.dev/hris/employees/) and [Employments](https://docs.merge.dev/hris/employments/) for ADP Workforce Now
- Support for “avatar” field under [Employees](https://docs.merge.dev/hris/employees/) for Rippling
- Support for home locations under [Locations](https://docs.merge.dev/hris/locations/) for CharlieHR
- Enhancements to “pay\_period” for hourly workers under [Employments](https://docs.merge.dev/hris/employments/) for BambooHR
- Enhancements to larger accounts linking for HiBob
- Enhancements to “start date” under [Employments](https://docs.merge.dev/hris/employments/) for Sapling
- Enhancements to [Groups](https://docs.merge.dev/hris/groups/) for BambooHR
- Support for “candidate” under [Activities](https://docs.merge.dev/ats/activities/) for Greenhouse, SAP, Workable, and JazzHR
- Support for [POST/Activities](https://docs.merge.dev/ats/activities/#activities_create) for BrassRing
- Enhancements to pagination optimizations to support larger accounts for iCIMs
- Fixed timeout issue with SAP SuccessFactors
- Enhancements to [POST/Candidates](https://docs.merge.dev/ats/candidates/#candidates_create) and [POST/Applications](https://docs.merge.dev/ats/applications/)  for SAP SuccessFactors
- Enhancements to [Jobs](https://docs.merge.dev/ats/jobs/) for BambooHR
- Enhancements to [Attachments](https://docs.merge.dev/ats/attachments/) for Taleo
- Enhancements to [Applications](https://docs.merge.dev/ats/applications/) for Taleo
- Enhancements to remote data for [Attachments](https://docs.merge.dev/ats/attachments/) for Greenhouse
- Support for deleted data coverage for Greenhouse via webhooks; Greenhouse will now immediately pull and update all deleted data with end user webhook setup
- Support for deleted data coverage for Xero via 3rd party API; Xero will now automatically pull and update any deleted transaction or reference data without any setup
- Support for “account” relation for Quickbooks Online
- Enhancements to transaction number for NetSuite
- Enhancements to pagination for [Journals](https://docs.merge.dev/accounting/journal-entries/) to pull missing transactions for Xero
- Enhancements to [Income Statement](https://docs.merge.dev/accounting/income-statements/) for Xero
- Enhancements to “names” under [Contacts](https://docs.merge.dev/accounting/contacts/) for Freshbooks and FreeAgent
- Enhancements to [Attachments](https://docs.merge.dev/accounting/attachments/) data erroring out for Quickbooks Online
- Enhancements to linking sandbox accounts for Netsuite
- Enhancements to /meta endpoints for Freshdesk
- Support for “linked\_account\_parameters” to /meta endpoints for Freshdesk and Freshservice
- Enhancements to with [Tickets](https://docs.merge.dev/ticketing/tickets/) and [Comments](https://docs.merge.dev/ticketing/comments/) data syncing for Shortcut
- Support [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) support for Height
- Enhancements to [POST/Notes](https://docs.merge.dev/crm/notes/#notes_create) for Salesforce
- Support for reserved XML characters under "name" and "description" fields for Salesforce [POST/Opportunity](https://docs.merge.dev/crm/opportunities/#opportunities_create) and [PATCH/Opportunity](https://docs.merge.dev/crm/opportunities/#opportunities_partial_update)
- Support for partner authentication and OAuth support for Dropbox

# **👨‍💻**

## SDK Updates

- Updated Python SDK to [v2.2.8](https://pypi.org/project/MergePythonSDK/)

May 31, 2023

https://www.merge.dev/changelog/week-1-june-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 1, June 2023

# **🖇️**

## New Integrations

We’re excited to expand our HRIS Unified API with the addition of [Deel SCIM](https://merge.dev/integrations/deel), which is now available in beta!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/6477903bd9da7005bc12f0f3_Deel%20SCIM%20Blog.webp)

We’re thrilled to expand our ATS Unified API with the addition of [Infinite BrassRing](https://merge.dev/integrations/infinite-brassring), which is now available in alpha!

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/64779049dbd1c272c868afb2_Inifinte%20BrassRing%20Blog.webp)

# **✨**

## Improvements

- Enhancements to null “work\_location” for ADP
- Enhancements to most recent Employment “employment\_type” and “pay\_period” fields for UKG Pro
- Enhancements to [Employments](https://docs.merge.dev/hris/employments/) for Charthop
- Support for additional field coverage for Azure Active Directory
- Enhancements to [POST/TimeOff](https://docs.merge.dev/hris/time-off/) requests for Ceridian Dayforce
- Enhancements to the [Employment](https://docs.merge.dev/hris/employments/) object syncs for Workday
- Enhancements to [Employees](https://docs.merge.dev/hris/employees/) to remove duplicates for Justworks
- Enhancements to ADP [Groups](https://docs.merge.dev/hris/groups/) “type” field to normalize to a standard enum value
- Enhancements to phone number values for Saplin
- Support for a new field on [JobInterviewStage](https://docs.merge.dev/ats/job-interview-stages/) “stage\_order” to signify hiring process stage; available in beta for Ashby, Greenhouse, Workable, Teamtailor, and Lever
- Enhancements to “credited\_to” field for JobAdder
- Enhancements to Workday Financial sync speed
- Enhancements to [Accounts](https://docs.merge.dev/accounting/accounts/) “status” field mapping for Workday Financial
- Support for a new field “tracking\_category” that has relations to Invoices, Vendor Credit, Expense, CreditNote, Payment, PurchaseOrder, Transaction for Quickbooks Online
- Support for a new field “tracking\_category” that has relations to VendorCredit, Transaction, Invoice for Netsuite
- Support for a new field “tracking\_category” that has relations to Transaction, Invoice, JournalEntry, CreditNote, PurchaseOrder for Microsoft Dynamics
- Added timestamp optimizations for ZohoBooks
- Enhancements to improve ClickUp’s rate limit detection
- Support for “ticket\_url” fields for Wrike, Hive, and Height
- Support for [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Freshservice
- Support for [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Height

May 23, 2023

https://www.merge.dev/changelog/week-4-may-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 4, May 2023

# **✨**

## Improvements

- Faster and streamlined customer support via Intercom by automatically surfacing the relevant linked account and/or issue
- Enhancements to Insperity authentication to support more url types
- Enhancements to “employment\_type” field for Justworks
- Enhancements with Ceridian Dayforce syncs to update [TimeOffBalances](https://docs.merge.dev/hris/time-off-balances/)
- Enhancements to timestamps for SAP SuccessFactors
- Enhancements to employment effective date for Sapling
- Added pagination and retry optimizations to Oracle Taleo
- Added hiring managers to [Remote Users](https://docs.merge.dev/ats/users/#users-object) for JobAdder
- Enhancements to remote data for iCIMs
- Enhancements to pagination to [applications](https://docs.merge.dev/ats/applications/) for Greenhouse
- Enhancements to [POST/Attachments](https://docs.merge.dev/ats/attachments/) for Workable
- Added optimizations for syncing [job interview stages](https://docs.merge.dev/ats/job-interview-stages/) for Greenhouse
- Added timestamp and rate limit optimizations to Zoho Books
- Added transaction ID to remote data for Netsuite
- Support for multi-subsidiary for Contacts/ Vendors for Netsuite
- Enhancements to [PATCH/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_partial_update) status for Jira
- Support for [Content Notes](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_contentnote.htm) under [GET/Notes](https://docs.merge.dev/crm/notes/) for Salesforce

# **👨‍💻**

## SDK Updates

- Updated Kotlin SDK to [v2.0.8](https://github.com/merge-api/merge-sdk-kotlin)
- Updated Typescript SDK to [v3.1.0](https://github.com/merge-api/merge-sdk-typescript)

May 16, 2023

https://www.merge.dev/changelog/week-3-may-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 3, May 2023

# **✨**

## Improvements

- Support for multi-subsidiary for [Contacts](https://docs.merge.dev/accounting/contacts/) for Netsuite
- Support for deleted data for Quickbooks Online
- Added deleted support for [collections](https://docs.merge.dev/ticketing/collections/) for Basecamp
- Enhancements to Salesforce writes for Remote Fields
- Enhancements to Merge Dashboard user interface

May 9, 2023

https://www.merge.dev/changelog/week-2-may-2023

![](https://cdn.prod.website-files.com/624b192df0b0151225c10026/62d8314333ef3768a6b9a6a8_Name%3DlinkLink%20Icon.svg)

URL Copied!

## Week 2, May 2023

# 💥

## Updates to Linked Account View in the Merge Dashboard

We are making major enhancements to Merge Dashboard’s [Linked Accounts section](https://app.merge.dev/linked-accounts/accounts) to make our integrations management capabilities even better to help your support teams easily identify and address end user errors. We are excited to rollout the following changes.

- We’ve added reference docs, API Tester, Help Center, and a Support button, so your support team can access a resource or contact support if there’s an issue with a specific Linked Account.
- We show a Linked Account’s metadata, data sync status and scope in a single view. This provides visibility in when data was last synced, relevant permission, and current sync status.
- Added advanced configuration settings, such as field mapping and sync frequencies speeds, highlighting these settings at each linked account level.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645bc6979ddbfc69d9e02332_Screenshot%202023-05-10%20at%209.29.34%20AM.webp)

There’s a brand new “Data” page so you can view and configure data sync and access settings for a specific Linked Account.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645bc6a9b80b14417e99d7e3_Screenshot%202023-05-10%20at%209.29.49%20AM.webp)

There’s a brand new "Logs" page under each Linked Account so you can access an instant view all API request logs and webhooks related to a specific Linked Account. You don’t need to filter down in the Logs page anymore.

![](https://cdn.prod.website-files.com/62796ab9647626cbab663f42/645bc6b1b1110131cb501949_Screenshot%202023-05-10%20at%209.30.02%20AM.webp)

# **✨**

## Improvements

- Updates to “Developers” role permissions; see [details](https://help.merge.dev/en/articles/5389520-what-do-the-different-permissions-mean-for-team-members-and-how-can-i-modify-them) here
- Enhancements to Sapling’s “employment\_type” under [Employments](https://docs.merge.dev/hris/employments/#employments-object) by properly normalizing values
- Enhancements to BambooHR’s “employment type” under [Employments](https://docs.merge.dev/hris/employments/#employments-object) for terminated employees
- Enhancements to [Groups](https://docs.merge.dev/hris/groups/) for SAP Successfactors
- Enhancements to pulling payroll data for Gusto
- Enhancements to validating credentials for Hibob
- Support for associating a stage to [GET/Interviews](https://docs.merge.dev/ats/interviews/#interviews_list) for Greenhouse
- Support for fields to pull region and selection status to [GET/Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Taleo
- Support for “job\_description” under [GET/Jobs](https://docs.merge.dev/ats/jobs/#jobs_list) for Taleo
- Enhancements to “contact\_name” under [GET/Contacts](https://docs.merge.dev/accounting/contacts/#contacts_list) for Zoho Books
- Enhancements to relation between invoices and accounts receivable payments for Quickbooks Online
- Support for passing in a custom “status” value to [POST/Ticket](https://docs.merge.dev/ticketing/tickets/#tickets_create) for Linear
- Added ability to pass in phone number to [POST/Contact](https://docs.merge.dev/crm/contacts/#contacts_create) for Salesforce

# **👨‍💻**

## SDK Updates

- Updated Python SDK to [v2.2.7](https://pypi.org/project/MergePythonSDK/) (now includes Field Mapping support)

### Subscribe to the Merge Changelog

Receive updates about new integrations and features

Your email

Thank you! Your submission has been received!

Oops! Something went wrong while submitting the form.

Qualified

## Looking to add integrations to your product?

Simply and securely add 100s of customer-facing integrations with one API

Get a demoChat with an expertDownload product integrations eBook

![](https://t.co/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=880d8de5-b069-4fe0-babc-6d200f79be92&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2fcf4efc-1ba8-44e9-a1c6-d2c606a3a886&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fchangelog&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)![](https://analytics.twitter.com/1/i/adsct?bci=4&dv=America%2FAdak%26en-US%2Cen%26Google%20Inc.%26Linux%20x86_64%26255%261280%261024%264%2624%261280%261024%260%26na&eci=3&event=%7B%7D&event_id=880d8de5-b069-4fe0-babc-6d200f79be92&integration=gtm&p_id=Twitter&p_user_id=0&pl_id=2fcf4efc-1ba8-44e9-a1c6-d2c606a3a886&tw_document_href=https%3A%2F%2Fwww.merge.dev%2Fchangelog&tw_iframe_status=0&txn_id=o7z1d&type=javascript&version=2.3.33)

![](https://bat.bing.com/action/0?ti=343102454&tm=gtm002&Ver=2&mid=e75d7da1-6e49-42ae-b5eb-9d320a542f15&bo=2&sid=27bee2e03e8e11f0946b571b68d27aa1&vid=27bf5f303e8e11f0ba31059ccc3a7f1e&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=1280&sh=1024&sc=24&tl=Merge%20Changelog&p=https%3A%2F%2Fwww.merge.dev%2Fchangelog&r=&lt=1298&evt=pageLoad&sv=1&asc=G&cdb=AQAQ&rn=333172)
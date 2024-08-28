---
title: Atlassian Jira
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/atlassian-jira.png')} alt="atlassian-jira" width="80"/>

***Version: 1.7  
Updated: Mar 29, 2024***

This integration is built specifically for Jira OnPrem (Server and Data Center) and provides a range of issue management capabilities.

## Actions

* **Add Comment** (*Notification*) - Adds a new comment to an issue.
* **Create Issue** (*Notification*) - Creates a new issue in the specified Jira project.
* **Delete Issue** (*Containment*) - Deletes the specified issue.
* **Get Attachments** *(Enrichment)* - Retrieves attachments from an issue and stores them in Cloud SOAR.
* **Get Issue** *(Enrichment)* - Returns an issue in JSON format.
* **Jira Issues Daemon** (*Daemon*) - Automatically pulls issues from the specified project.
* **List Comments** (*Enrichment*) - Returns all comments for an issue.
* **List Fields** (*Enrichment*) - Returns a list of all fields, both System and Custom.
* **List Issue Types** (*Enrichment*) - Returns a list of all issue types visible to the user.
* **List Projects** (*Enrichment*) - Returns all projects which are visible for the currently logged-in user.
* **List Statuses** (*Enrichment*) - Get all issue types with valid status values for a project.
* **List Transitions** (*Enrichment*) - Get a list of the transitions possible for this issue by the current user.
* **Search** (*Enrichment*) - Searches for issues using JQL.
* **Update Issue** (*Notification*) - Edits an issue.
* **Update Issue Status** (*Notification*) - Perform a transition on an issue.

## Atlassian Jira V2 configuration

1. Sign in to Jira with your Atlassian account.
1. On the left menu, search for Security and in API token click Create and manage API tokens.
1. Create your API token with your label.
1. Make sure you copy your new API token. You won’t be able to see this token again.

## Atlassian Jira V2 in Automation Service and Cloud SOAR

1. Access integrations in the [Automation Service](/docs/platform-services/automation-service/automation-service-integrations/#view-integrations) or [Cloud SOAR](/docs/cloud-soar/automation).
1. After the list of the integrations appears, search/look for the integration and click on the row.
1. The integration details will appear. Click on the **"+"** button to add new Resource.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/atlassian-jira-v2/atlassian-jira-v2-3.png')} style={{border:'1px solid gray'}} alt="atlassian-jira-v2-3" width="400"/>
1. Label and Populate all the required fields (\*).
    * **URL API**. https://your-atlassian-site.atlassian.net/
    * **Username**. Your email address.
    * **API Token**. Insert the previously copied token.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/atlassian-jira-v2/atlassian-jira-v2-4.png')} style={{border:'1px solid gray'}} alt="atlassian-jira-v2-4" width="400"/>
1. Optional fields in the resource are used for actions.
    * Populate Jira Project Name when using 'Issues Jira Daemon' action.
    * Populate Cloud SOAR URL and Cloud SOAR JWT (token) when using '**Add Issue Attachment To Incident**' action.
1. Click **SAVE**.
1. To make sure the resource is working, hover over the resource and then click the pencil icon that appears on the right.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/atlassian-jira-v2/atlassian-jira-v2-5.png')} style={{border:'1px solid gray'}} alt="atlassian-jira-v2-5" width="400"/>
1. Click **TEST SAVED SETTINGS**.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/atlassian-jira-v2/atlassian-jira-v2-6.png')} style={{border:'1px solid gray'}} alt="atlassian-jira-v2-6" width="400"/>
1. You should receive a successful notification in the bottom right corner.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/atlassian-jira-v2/atlassian-jira-v2-7.png')} style={{border:'1px solid gray'}} alt="atlassian-jira-v2-7" width="400"/>

## Category

Ticketing System

## Change Log

* June 3, 2019 - First upload
* April 5, 2021 - New actions added
* June 3, 2021 - New action added
* June 24, 2022 - New actions added:
    + Get Issue
    + Monitor Issue Status
* August 02, 2022 - Updated action: Create Issue (update the description field to support the new line)
* August 02, 2022 - New action added:
    + Get Issue Comments
* January 24, 2023
    + added hint for Host
    + solved issue for which the integration test will throw an error if no value for timeout is provided
    + set the timeout field as not required
* July 18, 2023 (v1.4) - Updated the integration with Environmental Variables
* January 9, 2024 (v1.5)
    + New Logo
    + The following actions have been renamed:
        - Add Comment To Issue: Add Comment
        - Add Issue Attachments To Incident: Get Attachments
        - Get Issue Comments: List Comments
        - List Issue Fields: List Fields
        - List Issue Status: List Statuses
        - List Project: List Projects
        - Search Into Issues Jira: Search
        - Set Issue Status: Update Issue Status
    + Please note that this update introduces BREAKING CHANGES: both the output mapping and some input fields have been revised and updated.
* February 14, 2024 (v1.6)
    * Enhanced "Create Issue" and "Update Issue" actions to support Jira custom fields
* March 29, 2024 (v1.7)
    * Create Issue Action updated to allow new lines in the description field

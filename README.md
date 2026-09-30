# power-platform-automation-lab.
Power Automate lab demonstrating simulated PIM activation notifications through Microsoft Teams and Outlook.
## Power Automate Notification Lab

# Power Platform Automation Lab

![Power Automate](https://img.shields.io/badge/Power_Automate-0066FF?style=for-the-badge)
![Microsoft Teams](https://img.shields.io/badge/Microsoft_Teams-6264A7?style=for-the-badge)
![Office 365 Outlook](https://img.shields.io/badge/Office_365_Outlook-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Notification_POC-Complete-2EA44F?style=for-the-badge)

> Built and verified a Power Automate workflow which sends simulated privileged access notifications through Microsoft Teams and Outlook.

## Goal

Practice workflow automation by building a notification proof of concept connected to an IAM use case.

The scenario represents an employee requesting temporary membership in a privileged group. A manual trigger sends sample request details to Teams and Outlook.

## Environment

| Component | Configuration |
|---|---|
| Tenant | KokoriLab |
| Automation platform | Microsoft Power Automate |
| Flow type | Instant cloud flow |
| Flow name | PIM Activation Request Notification |
| Trigger | Manually trigger a flow |
| Teams connector | Microsoft Teams |
| Email connector | Office 365 Outlook |
| Test recipient | KokoriLab lab account |
| Related project | Identity Governance Lab |

## Quick Summary

| Feature | Status | Evidence |
|---|---|---|
| Manual flow trigger | ✅ Verified | Successful test run |
| Teams notification | ✅ Verified | Message received in Workflows chat |
| Outlook notification | ✅ Verified | Email received in lab inbox |
| Combined workflow | ✅ Verified | Both notifications received from one run |
| Live PIM integration | 📋 Planned | No live integration implemented |
| Access approval | Separate in Entra PIM | No approval action in this flow |

## Skills Demonstrated

- Creating instant cloud flows in Power Automate.
- Connecting Microsoft Teams and Office 365 Outlook.
- Configuring authenticated connector connections.
- Delivering notifications across two channels.
- Testing workflow execution and confirming delivery.
- Documenting the boundary between notifications and access approval.

## What This Lab Covers

### 1. Manual Trigger — ✅ Complete

Created an instant cloud flow named **PIM Activation Request Notification**.

The **Manually trigger a flow** action starts the test. Request details are predefined sample text.

### 2. Microsoft Teams Notification — ✅ Complete

Added the **Post message in a chat or channel** action.

| Setting | Value |
|---|---|
| Post as | Flow bot |
| Post in | Chat with Flow bot |
| Recipient | Lab account |
| Message heading | PIM Activation Request — Lab Simulation |

Ran the flow and confirmed receipt in the Teams **Workflows** chat.

### 3. Outlook Email Notification — ✅ Complete

Added **Send an email (V2)** through the Office 365 Outlook connector after the Teams action.

| Setting | Value |
|---|---|
| Recipient | Lab account |
| Subject | PIM Activation Request — Lab Simulation |
| Body | Sample requester, group, duration, and reason |

Confirmed receipt in the lab inbox.

### 4. Combined Workflow Test — ✅ Complete

The flow executes these actions in sequence:

**Manual trigger → Teams message → Outlook email**

Verified successful flow execution and delivery through both channels.

### 5. Live PIM Integration — 📋 Planned

The current workflow has no connection to real PIM activation events.

A future extension would investigate Microsoft Graph access to PIM request data, authentication, required permissions, and a suitable detection approach.

## Test Scenario

| Field | Sample value |
|---|---|
| Requester | James Okafor |
| Target group | IT-Admins |
| Requested duration | 1 hour |
| Business reason | Troubleshoot an endpoint issue |

Both notifications explicitly identify the request as a lab simulation.

## Notification and Approval Boundary

| Current flow behaviour | Real PIM behaviour |
|---|---|
| Starts when manually run | Starts with an actual activation request |
| Sends predefined sample details | Records the submitted request |
| Delivers Teams and Outlook notifications | Applies configured activation requirements |
| Grants no access | Activates access after requirements are satisfied |
| Contains no approval action | Supports review by designated approvers |

Receiving a notification gives no approval authority. Real requests requiring approval are reviewed in Entra PIM.

## Notable Troubleshooting

| Observation | Resolution or decision |
|---|---|
| Searching for PIM returned no suitable native trigger | Used a manual trigger for the notification proof of concept |
| The earlier flow did not appear under My flows | Recreated the flow as an instant cloud flow and saved |
| Teams displayed the message under Workflows | Opened the Workflows chat and verified the sample details |
| The notification contained no approval button | Confirmed the action sends text and creates no PIM request |

## Screenshot Evidence

Verified evidence includes:

| Screenshot | Filename |
|---|---|
| Successful flow run | `pim-notification-flow-success.png` |
| Teams message | `pim-notification-teams.png` |
| Outlook email | `pim-notification-outlook.png` |

Screenshot uploads are pending.

<!--
After uploading all three files to the images folder:
1. Remove this comment block.
2. Replace "Screenshot uploads are pending." with the image sections below.

### Successful Flow Run

![Successful Power Automate flow run](images/pim-notification-flow-success.png)

### Teams Notification

![Simulated PIM notification received in Teams](images/pim-notification-teams.png)

### Outlook Notification

![Simulated PIM notification received in Outlook](images/pim-notification-outlook.png)
-->

## Documentation Approach

This repository records the lab goal, configuration, test results, troubleshooting, and supporting screenshots.

Completed features reflect observed results. Planned features are identified separately.

## Progress Log

| Date | Activity | Outcome |
|---|---|---|
| 2026-09-30 | Created the instant cloud flow | Manual trigger configured |
| 2026-09-30 | Added and tested the Teams action | Message received in Workflows chat |
| 2026-09-30 | Added and tested the Outlook action | Email received in lab inbox |
| 2026-09-30 | Tested the combined workflow | Both notifications received |
| 2026-09-30 | Confirmed the approval boundary | Notification flow grants no access |

## Biggest Lesson

Successful notification delivery does not prove integration with the source system. Detecting a real PIM request requires a separate integration.

## What This Lab Proves

I built, authenticated, tested, and verified a Power Automate workflow across two Microsoft 365 connectors.

## Next Steps

- Upload screenshots of the successful run and both notifications.
- Explore trigger inputs for reusable request details.
- Investigate Microsoft Graph integration with real PIM requests.

---

**Status:** Teams and Outlook notification proof of concept complete.

**License:** MIT



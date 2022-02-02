---
uid: community-invite
---

# Invite a tenant to a community

Before another tenant can join a community that you have creates, you must send them an invitation, they must accept it, and then you must confirm it. In other words, this process is a three-step handshake that requires collaboration between tenants.

**Note:** This document provides step-by-step instruction for the user that is inviting another tenant to a community. If you are looking for instructions on how to accept a community invitation, see <xref:community-accept-invite>.

**Reminder:** You must have the email address for the Tenant Administrator that you are inviting to the community as stated in the [prerequisites](xref:community-setup#prerequisites-for-community-setup).
## Step 1: Invite a tenant to the community

To invite another tenant to the community, follow these steps:

1. In the left pane, select **Data Management** > **Communities**.

1. Find the community you want to invite another tenant to and select **Details**.

1. On the **Tenants** tab, select **Invite Tenant**.

1. Enter the email address of the Tenant Administrator for the tenant you would like to invite. Then select **Invite**.

  An email is sent to the invited Tenant Administrator.

## Step 2: Wait for invited tenants to accept invitation

After you send an invitation to another tenant, wait for its tenant administrator to accept the email invitation.

**Tips:** 

- Share <xref:community-accept-invite> with the invited tenant administrator for instruction.

- If the invited tenant administrator does not receive the initial email invitation, you can resend it to them. For instructions, see [Resend email invitation](#resend-email-invitation). 

## Step 3: Confirm the invitation

To confirm an invitation, follow these steps:

1. In the left pane, select **Data Management** > **Communities**.

1. On the `Communities` overview page, find the community that you have invited another tenant to and select **Details**.

1. On the `Community Details` page, select the **Invitations** tab.

1. Select an invitation with a status of **Invitation Accepted**.

1. On the `Invitation Details` pane, select **Confirm Tenant**. When prompted for confirmation, select **Confirm Tenant** again.

  The invitee's tenant is now part of the community.

## What's next?

Edit permissions for data streams to allow tenant data stewards to share them with the community. For more information, see <xref:community-manage-sds-permissions>.

## Resend email invitation

If you invite another tenant to the community but its Tenant Administrator does not receive the invitation email, you can resend it. To resend an invitation, follow these steps:

1. In the left pane, select **Data Management** > **Communities**.

1. On the `Communities` overview page, find the community that you have invited another tenant to and select **Details**.

1. On the `Community Details` page, select the **Invitations** tab.

1. Find the **Invitation Recipient** who has not received the email invitation with a **Status** of `Invitation Pending`. Select the recipient, and then select **Resend Invitation**.
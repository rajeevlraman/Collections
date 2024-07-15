---
title: Conditional_Access_Policy_ex_email
description: Conditional_Access_Policy_ex_email
layout: libdoc/page

#LibDoc specific below
category: Features
order: 96
#unlisted: true
---
* 
{:toc}

## Overview
This policy ensures that only devices that comply with your organization's security standards can access email services. This helps to secure email communications by enforcing device compliance, such as having encryption enabled and up-to-date software.

## Steps to Create the Policy

### Step 1: Access Azure AD Conditional Access
1. Sign in to the [Azure Portal](https://portal.azure.com).
2. Navigate to **Azure Active Directory**.
3. In the left-hand menu, select **Security**.
4. Click on **Conditional Access**.

### Step 2: Create a New Policy
1. In the **Conditional Access** section, click on **New policy**.
2. Name the policy, e.g., "Require Compliant Devices for Email Access".

### Step 3: Configure Assignments
1. **Users and Groups**:
   - Click on **Users and groups**.
   - Choose **All users** or select specific groups (e.g., employees).
   - Click **Select** to confirm.

2. **Cloud Apps or Actions**:
   - Click on **Cloud apps or actions**.
   - Select **Include** > **Select apps**.
   - Search for and choose the email services (e.g., **Office 365 Exchange Online**).
   - Click **Select** to confirm.

3. **Conditions**:
   - Expand the **Device state** condition.
   - Click on **Configure** and set it to **Yes**.
   - Under **Include**, select **All device states**.
   - Under **Exclude**, select **Compliant** to exclude compliant devices from further controls (since we only want non-compliant devices to be blocked or restricted).
   - Click **Done**.

### Step 4: Configure Access Controls
1. **Grant**:
   - Click on **Grant**.
   - Select **Require device to be marked as compliant**.
   - Click **Select** to confirm.

### Step 5: Enable and Save the Policy
1. Review all the configured settings.
2. Set the policy status to **On**.
3. Click **Create** to save and activate the policy.

## Summary
This policy enforces that only compliant devices can access your organization's email services. It protects email data by ensuring devices adhere to security standards.

![Conditional Access Policy - Compliant Devices](https://via.placeholder.com/800x400.png?text=Conditional+Access+Policy+-+Compliant+Devices)

---

### Scenario 4: Block Access from Risky Sign-In Locations

```markdown
# Conditional Access Policy: Block Access from Risky Sign-In Locations

## Overview
This policy blocks access to organizational resources from locations that are deemed high-risk. This includes regions with a history of security issues or no legitimate user presence. It helps to prevent unauthorized access and potential security breaches from these locations.

## Steps to Create the Policy

### Step 1: Access Azure AD Conditional Access
1. Sign in to the [Azure Portal](https://portal.azure.com).
2. Navigate to **Azure Active Directory**.
3. In the left-hand menu, select **Security**.
4. Click on **Conditional Access**.

### Step 2: Create a New Policy
1. In the **Conditional Access** section, click on **New policy**.
2. Name the policy, e.g., "Block Access from Risky Locations".

### Step 3: Configure Assignments
1. **Users and Groups**:
   - Click on **Users and groups**.
   - Choose **All users** or select specific groups that should be protected.
   - Click **Select** to confirm.

2. **Cloud Apps or Actions**:
   - Click on **Cloud apps or actions**.
   - Select **All cloud apps** to apply this policy to all applications.
   - Click **Select** to confirm.

3. **Conditions**:
   - Expand the **Locations** condition.
   - Click on **Configure** and set it to **Yes**.
   - Under **Include**, select **All locations**.
   - Under **Exclude**, select **Trusted locations** to allow access from recognized safe locations (like your corporate network).
   - To include specific risky locations, click on **Named locations** and select or define locations with high risk.
   - Click **Done**.

### Step 4: Configure Access Controls
1. **Grant**:
   - Click on **Grant**.
   - Select **Block access**.
   - Click **Select** to confirm.

### Step 5: Enable and Save the Policy
1. Review all the configured settings.
2. Set the policy status to **On**.
3. Click **Create** to save and activate the policy.

## Summary
This policy blocks access to your organizational resources from high-risk locations, enhancing security by preventing unauthorized access from these areas.

![Conditional Access Policy - Block Risky Locations](https://via.placeholder.com/800x400.png?text=Conditional+Access+Policy+-+Block+Risky+Locations)

---

*Note: These guides provide step-by-step instructions for creating specific Conditional Access policies in Azure AD. For more complex configurations or additional security scenarios, refer to the official [Microsoft Azure documentation](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/).*

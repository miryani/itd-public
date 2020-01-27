---
title: "Okta Reset/Change Password"
date: 2020-01-24T11:25:00-06:00
draft: false
---

# How-to Enable Reset Password Through Okta Feature and Use It

This document explains how-to enable Reset Password feature on Okta and how-to use it.

---

{{< hint danger >}}
**Note**  
Resetting/updating password through Okta will be propagated into Active Directory and Email Server, immediately. Therefor; Okta, Active Directory and Email accounts eventually will have the same password. To sync your laptop password with the new password in real-time, the VPN must be connected, otherwise; the old password must be used to login into laptop (either Windows or macOS). When your laptop is connected to the VPN or Office Network, the laptop password is synced immediately.
{{< /hint >}}


## Pre-Requirements and Steps to Reset Password

### Pre-Requirements
1. To enable resetting password, the **"Forget Password Text Message"** feature must be enabled. See the [**instructions to ...**]({{< relref "#instructions-to-enable-forget-password-text-message-feature" >}}) below.
2. Make sure you have already set and know your **"Forgotten Password Question"** and its **answer**. This question and answer can be found and edited at: **Okta > Under Your Name > Settings > Forgotten Password Question**

{{< hint danger >}}
**Note**  
Before resetting the password through OKTA, Outlook must be closed as well as on your smartphone and any other mobile devices must be offline (if you have DMD email account configured on any mobile device).
{{< /hint >}}

### Steps to Rest Password
1. Open Okta
2. Click "Need help signing in?"
3. Click "Forgot Password"
4. Follow the steps as they are asked
5. After resetting password, bring outlook and mobile devices online one-by-one and enter the new password when it is asked.

---

## Instructions to Enable "Forget Password Text Message" Feature


{{< tabs "tabs_users" >}}
{{< tab "Current Users" >}}
# Current Users

1. Login into Okta with the current credentials
2. You will be asked to update your profile by adding "phone number"
3. Verify the entered phone number by clicking "Send Code" and entering the received passcode.

{{< /tab >}}
{{< tab "New Users" >}}

# New Users

1. Login into Okta with the current credentials
2. Fill out the requested fields on the form:
+ Secondary Email: is optional - It can be your personal email asl well. Already DMD email account has enrolled for each user.
+ Choose a forgot password question: required.
+ Answer is required. At least 4 characters for the answer.
+ Add a phone number to resett your password or unlock your account using SMS (optional), however; it strongly recommended. **Country** , **Phone number**
3. Verify the phone number by clicking "Send Code" and entering the received passcode
4. Click "Create My Account"

{{< /tab >}}
{{< /tabs >}}



---
- Author: M. Miryani | Created: 2020-01-24T11:25:00-06:00
---

# Configure Single Sign-On (SSO) for a SaaS Application using Microsoft Entra ID

## Summary
This lab demonstrates how to configure Single Sign-On (SSO) for a third-party SaaS application using Microsoft Entra ID (formerly Azure Active Directory). The objective is to enable seamless authentication for users, eliminating the need for multiple credentials while enhancing security and access control. The lab guides through setting up SAML-based authentication, assigning users, and testing the login process.

## Definition: Single Sign-On (SSO)
Single Sign-On (SSO) is an authentication process that allows users to access multiple applications with a single set of credentials. Microsoft Entra ID supports various SSO methods, including SAML, OAuth, OpenID Connect, and password-based authentication. Implementing SSO enhances security by centralizing authentication, reducing password fatigue, and enforcing access policies.

### Definition: Security Assertion Markup Language (SAML)
SAML is an open standard that enables identity providers (IdPs) to securely exchange authentication and authorization data with service providers (SPs). It allows users to log in once and gain access to multiple applications without re-entering credentials. SAML uses XML-based assertions to pass authentication information between entities.

### Definition: OAuth
OAuth is an open-standard authorization framework that allows third-party applications to access a user's data without exposing credentials. It uses access tokens issued by an authorization server to grant limited access to resources on behalf of the user. OAuth is commonly used for API security and delegated access.

### Definition: OpenID Connect (OIDC)
OpenID Connect is an identity layer built on top of OAuth 2.0, enabling applications to verify user identities based on authentication performed by an identity provider. OIDC provides ID tokens containing user details and is widely used for modern web and mobile authentication.

## Lab Requirements
Before starting this lab, ensure the following requirements are met:

- **Microsoft Entra ID Admin Access** – Access to the Microsoft Entra Admin Center with Global Administrator or Application Administrator permissions.
- **SaaS Application with SSO Support** – An application that supports SAML-based authentication (e.g., Salesforce, ServiceNow, Google Workspace, or Dropbox).
- **Test User Account** – A non-administrator account for verifying SSO login.
- **Internet Connection** – Required to access the Microsoft Entra Admin Center.

## Who
This lab is intended for IT administrators, security analysts, and identity management professionals responsible for configuring and managing authentication for SaaS applications in Microsoft Entra ID.

## What
The lab involves configuring a SaaS application to use SAML-based authentication through Microsoft Entra ID, assigning users, and verifying the login process.

## When
This lab is applicable when:

- Deploying a new SaaS application in an organization.
- Enhancing authentication security through centralized access management.
- Reducing the need for multiple user credentials.
- Implementing compliance-based access control policies.

## Where
This lab is performed within the **Microsoft Entra Admin Center** under the **Enterprise Applications** and **Identity** sections.

## Why
Enabling SSO for SaaS applications is critical for:

- Reducing the risk of credential theft and phishing.
- Improving user experience with seamless authentication.
- Enforcing access policies across multiple applications.
- Streamlining IT operations and reducing password reset requests.

## Step-by-Step Guide

### Step 1: Register the SaaS Application in Microsoft Entra ID
1. Sign in to the **Microsoft Entra Admin Center** at [https://entra.microsoft.com](https://entra.microsoft.com).
2. Navigate to **Enterprise Applications** > **New Application**.
3. Search for the SaaS application (e.g., Salesforce, Dropbox, Google Workspace) and select it.
4. Click **Add** to register the application.

### Step 2: Configure Single Sign-On (SSO)
1. In the **Enterprise Applications** section, select the newly added application.
2. Under the **Manage** menu, select **Single sign-on**.
3. Choose **SAML** as the SSO method.
4. Click **Edit** in the **Basic SAML Configuration** section and enter the required information:
   - **Identifier (Entity ID)** – Provided by the SaaS application.
   - **Reply URL (Assertion Consumer Service URL)** – Provided by the SaaS application.
   - **Sign-on URL** – The login URL for the application.
5. Save the configuration and download the **Federation Metadata XML** file or copy the **App Federation Metadata URL**.

### Step 3: Assign Users and Groups
1. Go to **Users and Groups** in the application settings.
2. Click **Add User/Group** and select the users or groups who need access.
3. Click **Assign** to grant access.

### Step 4: Configure the SaaS Application for SAML Authentication
1. Log in to the SaaS application's admin portal.
2. Navigate to the **SSO Settings** or **Identity Provider (IdP) Configuration**.
3. Upload the **Federation Metadata XML** or enter the **Microsoft Entra ID SAML Endpoint** manually.
4. Save the changes and enable SSO authentication.

### Step 5: Test the SSO Login Flow
1. Open a new browser window and navigate to the **SaaS application's login page**.
2. Click **Sign in with Microsoft Entra ID** or use the direct login URL.
3. Enter Entra ID credentials when prompted.
4. Verify successful authentication and access to the application.

### Step 6: Monitor and Troubleshoot SSO Authentication
1. In the **Microsoft Entra Admin Center**, navigate to **Sign-in logs** under **Monitoring**.
2. Filter logs by the application to check login attempts.
3. Troubleshoot any authentication issues using error codes and recommendations.

## Conclusion
This lab demonstrated how to configure **SAML-based Single Sign-On (SSO)** for a SaaS application using **Microsoft Entra ID**. By enabling SSO, organizations can enhance security, improve user experience, and enforce centralized authentication policies. Further configurations can include **Multi-Factor Authentication (MFA)** and **Conditional Access policies** for additional security layers.


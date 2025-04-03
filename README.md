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
![image](https://github.com/user-attachments/assets/d95efa8d-7641-4f5a-b59a-b2e80a78886e)
![image](https://github.com/user-attachments/assets/c4412b64-2a59-4799-a5f9-fbd240c80acf)

3. Search for the SaaS application Dropbox and select it.
![image](https://github.com/user-attachments/assets/25440004-f9c5-41f4-af1f-8888d6d8215a)
![image](https://github.com/user-attachments/assets/f0cab8f4-a771-4b7b-9a11-8cf74d49a308)

### Step 2: Configure Single Sign-On (SSO)
1. In the **Enterprise Applications** section, select the newly added application.
2. Under the **Manage** menu, select **Single sign-on**.
![image](https://github.com/user-attachments/assets/82df5c1a-da58-4796-b67b-86c7270ad110)

3. Choose **SAML** as the SSO method.
![image](https://github.com/user-attachments/assets/1f17faf3-648b-4fa2-a697-cac87b8bbd36)

4. Click **Edit** in the **Basic SAML Configuration** section and enter the required information:
![image](https://github.com/user-attachments/assets/07c2f8fc-43ae-431c-93d5-3362f63319bc)

    - **Identifier (Entity ID)** – Provided by the SaaS application.
   - **Reply URL (Assertion Consumer Service URL)** – Provided by the SaaS application.
   - **Sign-on URL** – The login URL for the application.
![image](https://github.com/user-attachments/assets/6ffb9402-340c-4ad4-82dd-21811f350566)

6. Save the configuration and download the **Federation Metadata XML** file or copy the **App Federation Metadata URL**.
![image](https://github.com/user-attachments/assets/585f47ea-e04b-407c-a03e-df6e91adb04a)

### Step 3: Assign Users and Groups
![image](https://github.com/user-attachments/assets/e9f8cb23-57b0-4ef3-aaeb-4211b1ba33c3)

1. Go to **Users and Groups** in the application settings.
2. Click **Add User/Group** and select the users or groups who need access.
![image](https://github.com/user-attachments/assets/bf36e5cc-1ed5-4a43-8895-923ba2d26f6d)

3. Click **Assign** to grant access.
![image](https://github.com/user-attachments/assets/42cedbf7-0237-42c1-bdfe-c3aa712f9f8a)

### Step 4: Configure the SaaS Application for SAML Authentication
1. Log in to the SaaS application's admin portal.
2. Navigate to the **SSO Settings** or **Identity Provider (IdP) Configuration**.
![image](https://github.com/user-attachments/assets/634839eb-4b0e-41e1-9abf-31ee4d7050e9)

3. Upload the **Federation Metadata XML** or enter the **Microsoft Entra ID SAML Endpoint** manually.
![image](https://github.com/user-attachments/assets/125451b9-2f88-472f-acac-ceee8b6fc9a6)

4. Download the Certificate (Base64) to add into the DropBox admin console.
![image](https://github.com/user-attachments/assets/0eb8ebf8-e86d-42aa-b066-6c4033b4b57c)

![image](https://github.com/user-attachments/assets/657fb711-5750-496d-a82f-3c8145ad394e)

5. Save the changes and enable SSO authentication.

### Step 5: Test the SSO Login Flow
1. Open a new browser window and navigate to the **SaaS application's login page**.
![image](https://github.com/user-attachments/assets/951645cf-8387-4aab-bfcb-ff027d6c8dc3)

2. Verify successful authentication and access to the application.
![image](https://github.com/user-attachments/assets/08e94844-f7af-487d-a262-b5f160a691b0)


## Conclusion
This lab demonstrated how to configure **SAML-based Single Sign-On (SSO)** for a SaaS application using **Microsoft Entra ID**. By enabling SSO, organizations can enhance security, improve user experience, and enforce centralized authentication policies. Further configurations can include **Multi-Factor Authentication (MFA)** and **Conditional Access policies** for additional security layers.


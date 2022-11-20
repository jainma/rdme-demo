---
title: "Configure Developer Portal access"
excerpt: "Welcome to the Dimensions REST API Excerpt..."
---

# Configure Developer Portal access

Follow the instructions in this topic to grant a user permission to access the Developer Portal as a developer or administrator. Developers can access the full breadth of the Dimensions API documentation available on the portal. Administrators can also generate application (app) keys. For more information on app keys, refer to the [Generate and access app keys](C:a44a9f41-6442-42e3-91b1-9c946de54763) topic.

* [Log in and navigate to Function Access Profiles](#LogInToTheSuiteUI)
* [Configure Developer Portal access](#ConfigureDevPortalAccess)
* [Configure Administrator access to the Developer Portal](#ConfigureAdminAccess)

## Log in and navigate to Function Access Profiles {#LogInToTheSuiteUI}

To log in to the suite UI and navigate to Function Access Profiles: 

1. Log in to the Dimensions user interface as a manager with full Developer Portal access permissions.
2. Open the **Main Menu**, select **Administration**, and select **Application setup**.
3. Under Access Profiles, select **Function Access Profiles**.

## Configure Developer Portal access {#ConfigureDevPortalAccess}

Select and configure the Function Access Profile (FAP) assigned to the user or users to whom you wish to grant Developer Portal access.

To grant access to the Developer Portal:

1. Select the appropriate FAP. You may also check the checkbox next to the appropriate FAP and select **Edit**.
2. Select **Manager - Common Setup** to expand the section.
3. Select **Developer Portal** to expand the subsection and display the Administrator Access and Developer Access options.
4. To grant access to the Developer Portal, select **Allowed** from the Developer Access drop-down menu.
5. Select **Save** or **Save & Return**.

The user or users associated with the configured FAP are now able to log in, open the **Main Menu**, select **Administration**, and select **Developer Portal** to access the Developer Portal. These users are also able to to log in, open the **Main Menu**, select **Administration**, **Application Setup**, **Common Setup**, and **My Apps** to [access app keys](C:a44a9f41-6442-42e3-91b1-9c946de54763) created by an Administrator.

> **Note:** Users granted access to the Developer Portal must have both the `FirstName` and `EmailAddress` optional fields filled in the People Editor.

## Configure Administrator access to the Developer Portal {#ConfigureAdminAccess}

Select and configure the Function Access Profile (FAP) assigned to the user or users to whom you wish to grant Developer Administrator access. Administrator access allows a user to generate app keys.

To grant Administrator access:

1. Select the appropriate FAP. You may also check the checkbox next to the appropriate FAP and select **Edit**.
2. Select **Manager - Common Setup** to expand the section.
3. Select **Allowed** from the Developer Portal drop-down menu. Selecting **Allowed** at this level automatically changes both the Developer Access and Administrator Access options to **Allowed**.
4. Select **Save** or **Save & Return**.

The user or users associated with the configured FAP are now able to log in, open the **Main Menu**, select **Administration**, **Application Setup**, **Common Setup**, and **My Apps** to [generate and edit app keys](C:a44a9f41-6442-42e3-91b1-9c946de54763).
---
title: Integrated with Active Directory
uid: web_api_auth_ad
description: Web API authentication Active Directory
author: {github-id}
so.date: 
keywords: 
so.topic: concept 
---

# Integrated with Active Directory

## SuperOffice Users

To integrate with Active Directory, you need to set up your SuperOffice users as Active Directory users.

* *web.config* must define and configure the `ActiveDirectoryCredentialPlugin` section.
* Your SuperOffice users need to be linked to Active Directory users.

## SuperOffice web.config

You must explicitly enable the authentication methods you want to use in the *web.config* file.

```XML
<WebApi>
  <add key="AuthorizeWithImplicit" value="true" />
</WebApi>
```

**AuthorizeWithImplicit** must be `true` otherwise the Active Directory authentication method will not work. It adds the `WWW-Authenticate: Negotiate` header that kicks off windows authentication.

## IIS configuration

1. Open the IIS Configuration tool and select the SuperOffice application.

2. In IIS, navigate to the application hosting SuperOffice web client.

3. Enable Windows Authentication, and disable the others.

    ![iis-authentication-windows][img1]

4. Click **Advanced Settings** to enable Kernel-mode authentication.

    ![iis-kernel-mode-auth][img2]

5. Click **Providers** to ensure that **Negotiate** is the first enabled provider.

    ![iis-auth-providers][img3]

Your SuperOffice and WebAPI should now be accessable without logging in.

The HTTP.sys kernel driver will stop unauthenticated requests before they reach ASP.net and send back an ActiveDirectory response that the browser can use to log in using its windows identity.

Accessing `/api/v1/user/currentPrincipal` via Chrome or Edge should automatically log you in, and return the current user's info.

<!-- Referenced images -->
[img1]: media/iis-authentication-windows.png
[img2]: media/iis-kernel-mode-auth.png
[img3]: media/iis-auth-providers.png
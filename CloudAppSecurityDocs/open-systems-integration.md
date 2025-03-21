---
title: Integrate with Open Systems
description: This article describes how to integrate Microsoft Defender for Cloud Apps with Open Systems for seamless Cloud Discovery and automated block of unsanctioned apps.
ms.date: 01/29/2023
ms.topic: how-to
---
# Integrate Defender for Cloud Apps with Open Systems

[!INCLUDE [Banner for top of topics](includes/banner.md)]

If you work with both Defender for Cloud Apps and Open Systems, you can integrate the two products to enhance your security Cloud Discovery experience. Open Systems, as a standalone Secure Web Gateway, monitors your organization's traffic enabling you to set policies for blocking transactions. Together, Defender for Cloud Apps and Open Systems provide the following capabilities:

- Seamless deployment of Cloud Discovery - Use Open Systems to proxy your traffic and send it to Defender for Cloud Apps. This eliminates the need for installation of log collectors on your network endpoints to enable Cloud Discovery.
- Open Systems' block capabilities are automatically applied on apps you set as unsanctioned in Defender for Cloud Apps.

## Prerequisites

- A valid license for Microsoft Defender for Cloud Apps
- A valid license for Open Systems Secure Web Gateway

## Deployment

1. Contact your Technical Account Manager in Open Systems to get the *Microsoft Cloud App Security with Secure Web Gateway Configuration Guide* to integrate the products.
1. Investigate cloud apps discovered on your network. For more information and investigation steps, see [Working with Cloud Discovery](working-with-cloud-discovery-data.md).
1. Any app that you set as unsanctioned in Defender for Cloud Apps will be retrieved by Open Systems, and then automatically blocked. It can take up to one hour for the app to be blocked on the Open Systems Secure Web Gateway. If you need the app to be blocked immediately after tagging it as **Unsanctioned**, contact Open Systems customer support. For more information about unsanctioning apps, see [Sanctioning/unsanctioning an app](governance-discovery.md#sanctioningunsanctioning-an-app).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]

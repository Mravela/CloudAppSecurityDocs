---
title: Classic portal -  Integrate with Zscaler
description: Classic portal -  This article describes how to integrate Microsoft Defender for Cloud Apps with Zscaler for seamless Cloud Discovery and automated block of unsanctioned apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Integrate Defender for Cloud Apps with Zscaler

[!INCLUDE [Banner for top of topics](includes/banner.md)]

If you work with both Defender for Cloud Apps and Zscaler, you can integrate the two products to enhance your security Cloud Discovery experience. Zscaler, as a standalone cloud proxy, monitors your organization's traffic enabling you to set policies for blocking transactions. Together, Defender for Cloud Apps and Zscaler provide the following capabilities:

- Seamless deployment of Cloud Discovery - Use Zscaler to proxy your traffic and send it to Defender for Cloud Apps. This eliminates the need for installation of log collectors on your network endpoints to enable Cloud Discovery.
- Zscaler's block capabilities are automatically applied on apps you set as unsanctioned in Defender for Cloud Apps.
- Enhance your Zscaler portal with the Defender for Cloud Apps risk assessment for 200 leading cloud apps, which can be viewed directly in the Zscaler portal.

## Prerequisites

- A valid license for Microsoft Defender for Cloud Apps, or a valid license for Microsoft Entra ID P1
- A valid license for Zscaler Cloud 5.6
- An active Zscaler NSS subscription

## Deployment

1. In the Zscaler portal, do the steps to complete the [Zscaler partner integration with Microsoft Defender for Cloud Apps](https://help.zscaler.com/zia/configuring-mcas-integration).
2. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), do the following integration steps:
    1. Select the settings cog and then select **Cloud Discovery Settings**.
    2. Select the **Automatic log upload** tab and then select **Add data source**.
    3. In the **Add data source** page, enter the following settings:

        - Name = NSS
        - Source = Zscaler QRadar LEEF
        - Receiver type = Syslog - UDP

        ![data source Zscaler.](media/classic-data-source-zscaler.png)

        > [!NOTE]
        > Make sure the name of the data source is **NSS.** For more information about setting up NSS feeds, see [Adding Defender for Cloud Apps NSS Feeds](https://help.zscaler.com/zia/adding-mcas-nss-feeds).

    4. Select **View sample of expected log file**. Then select **Download sample log** to view a sample discovery log, and make sure it matches your logs.<br />

3. Investigate cloud apps discovered on your network. For more information and investigation steps, see [Working with Cloud Discovery](working-with-cloud-discovery-data.md).

4. Any app that you set as unsanctioned in Defender for Cloud Apps will be pinged by Zscaler every two hours, and then automatically blocked by Zscaler. For more information about unsanctioning apps, see [Sanctioning/unsanctioning an app](governance-discovery.md#sanctioningunsanctioning-an-app).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]

---
title: Classic portal -  Access policies
description: Classic portal -  This article describes the procedure for setting up a Defender for Cloud Apps Conditional Access App Control access policy to allow and block access to apps connected through Microsoft Entra ID using reverse proxy capabilities.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Access policies in Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Defender for Cloud Apps access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app. You can create access policies for any device, including devices that aren't Microsoft Entra hybrid join, and not managed by Microsoft Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates. For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.

> [!NOTE]
> Instead of allowing or blocking access completely, with [session policies](session-policy-aad.md) you can allow access while monitoring the session and/or limit specific session activities.

## Prerequisites to using access policies

- Microsoft Entra ID P1 license, or the license required by your identity provider (IdP) solution
- The relevant apps should be [deployed with Conditional Access App Control](proxy-deployment-aad.md)
- Make sure you have configured your IdP solution to work with Defender for Cloud Apps, as follows:
  - For [Microsoft Entra Conditional Access](/azure/active-directory/conditional-access/overview), see [Configure integration with Microsoft Entra ID](proxy-deployment-aad.md#configure-integration-with-azure-ad)
  - For other IdP solutions, see [Configure integration with other IdP solutions](proxy-deployment-featured-idp.md#configure-integration-with-other-idp-solutions)

## Create a Defender for Cloud Apps access policy

To create a new access policy, follow this procedure:

1. Go to **Control** > **Policies** > **Conditional access**.

1. Select **Create policy** and then select **Access policy**.

    ![Create a Conditional access policy.](media/classic-create-policy-from-conditional-access-tab.png)

1. In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.

1. In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy. Filters include the following options:

    - **Device tags**: Use this filter to identify unmanaged devices.

    - **Location**: Use this filter to identify unknown (and therefore risky) locations.

    - **IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.

    - **User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or does not equal. The values should be tested against your mobile and desktop apps for each cloud app.

1. Under **Actions**, select one of the following options:

    - **Test**: Set this action to explicitly allow access according to the policy filters you set.

    - **Block**: Set this action to explicitly block access according to the policy filters you set.

1. You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email.

## Related videos

> [!div class="nextstepaction"]
> [Conditional Access App Control webinar](webinars.md#on-demand-webinars)

## Next steps

> [!div class="nextstepaction"]
> [« PREVIOUS: How to create a session policy](session-policy-aad.md)

> [!div class="nextstepaction"]
> [NEXT: Explore popular use cases »](use-case-proxy-block-session-aad.md)

## See also

> [!div class="nextstepaction"]
> [Blocking downloads on unmanaged devices using session controls](use-case-proxy-block-session-aad.md)

> [!div class="nextstepaction"]
> [Troubleshooting access and session controls](troubleshooting-proxy.md)

[!INCLUDE [Open support ticket](includes/support.md)]

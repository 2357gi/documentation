---
title: Sharing
kind: documentation
aliases:
    - /graphing/faq/is-there-a-way-to-share-graphs
    - /graphing/faq/is-there-a-way-to-share-or-revoke-previously-shared-graphs
    - /graphing/dashboards/shared_graph/
further_reading:
- link: "/dashboards/"
  tag: "Documentation"
  text: "Create Dashboards in Datadog"
- link: "/dashboards/template_variables/"
  tag: "Documentation"
  text: "Enhance your Dashboards with Template Variables"
- link: "/dashboards/widgets/"
  tag: "Documentation"
  text: "Discover Widgets for your Dashboard"
---

## Overview

Shared dashboards and graphs allow you to display metric, trace, and log visualizations outside of Datadog.

## Dashboards
When you share a dashboard by URL or email link, the shared page shows live, read-only contents of that dashboard. Widgets based on APM traces queries do not display data on public dashboards. The Log Stream widget doesn't show data either, but other Log-based queries do.

If your shared dashboard has visible tags configured, [template variable][4] selectors are present on the shared page. The template variables' default values are the default values you set when you configure the share, as described next.
### Share a dashboard by public URL

To share an entire dashboard publicly, generate a URL:

1. On the dashboard's page, click the settings cog in the upper right.
2. Select **Generate public URL**.
3. Under **Time & Variable Settings**, configure your desired options for the time frame and whether users can change it, as well which tags are visible for selectable template variables.
4. Copy the URL and click **Done**.

**Share with individual emails**: 
1. On the dashboard's page, click the settings cog in the upper right.
2. Select **Generate public URL**.
3. Select **Only specified people** for indicating who can access this dashboard.
4. Input the email addresses for people you would like to share your dashboard with.
5. CUnder **Time & Variable Settings**, configure your desired options for the time frame and whether users can change it, as well which tags are visible for selectable template variables.
6. (Optional) You can copy the URL to share; the specified email addresses will also receive an email with a link.
7. Click **Done**.

**Note**: 
- The created URL has live, read-only access to the contents of that specific dashboard.
- Dashboard [template variable][4] selectors are only present on dashboards when you configure visible tags. The template variables' default values are the default values set in Datadog. 
- Additionally, widgets based on APM traces queries do not display data on public dashboards. All log based queries will show data, except the Log Stream widget.

### Revoke

To revoke a shared dashboard:

1. Navigate to the [Dashboard List][5].
2. Select the dashboard you want to revoke access to.
3. Click on the settings cog in the upper right.
4. Click **Configure sharing**.
5. Click **Revoke public URL**.

## Graphs

### Share

To share a graph from a [Timeboard][1] or [Screenboard][2]:

2. For the graph you want to share, click the pencil icon in the upper right corner.
3. Under the *Graph your data* section, select the **Share** tab.
4. Pick a timeframe for your graph.
5. Pick a graph size.
6. Choose to include the legend or not.
7. Get the embed code with the *Generate embed code* button.

{{< img src="dashboards/sharing/share_graph.png" alt="Shared graph"  style="width:75%;">}}

### Revoke

To revoke the keys used to share individual (embedded) graphs:

1. Navigate to [**Integrations -> Embeds**][3] to see a list of all shared graphs.
2. Click on the **Revoke** button next to the graph you want to stop sharing.
3. The graph is moved to the **Revoked** list.

### Applying restrictions

You can restrict access on a per IP address basis to your dashboard. Email [Datadog support][6] to enable the IP address include listing feature that allows administrators to provide a list of IP addresses that have access to shared dashboards. Once enabled, manage your restrictions on your organization's [security page][7].

### Dark mode

Dark mode is available on public dashboards for individual users. Click the sun or moon icon in the upper right to toggle between modes. Additionally, the URL parameter `theme` is available. The possible values are `dark` and `light`.

### TV mode

TV mode is available on public screenboards. Use the keyboard shortcut `F` or click the TV icon in the upper right.

## API

Datadog has a [dedicated API][8] allowing you to interact with your shared graphs (embeds):

| Endpoint                 | Description                                                             |
|--------------------------|-------------------------------------------------------------------------|
| [Get all embeds][9]     | Get a list of previously created embeddable graphs.                     |
| [Create embed][10]       | Creates a new embeddable graph.                                         |
| [Get specific embed][11] | Get the HTML fragment for a previously generated embed with `embed_id`. |
| [Enable embed][12]       | Enable the specified embed.                                             |
| [Revoke embed][13]       | Revoke the specified embed.                                             |

## Further Reading

{{< partial name="whats-next/whats-next.html" >}}

[1]: /dashboards/timeboard/
[2]: /dashboards/screenboard/
[3]: https://app.datadoghq.com/account/settings#embeds
[4]: /dashboards/template_variables/
[5]: https://app.datadoghq.com/dashboard/lists
[6]: /help/
[7]: https://app.datadoghq.com/account/org_security
[8]: /api/v1/embeddable-graphs/
[9]: /api/v1/embeddable-graphs/#get-all-embeds
[10]: /api/v1/embeddable-graphs/#create-embed
[11]: /api/v1/embeddable-graphs/#get-specific-embed
[12]: /api/v1/embeddable-graphs/#enable-embed
[13]: /api/v1/embeddable-graphs/#revoke-embed

# Add a route map {#task_1478669 .task}

This topic describes how to add a route map to a CEN instance. Before you can use the route map function, you must add a route map. After you add a route map to a CEN instance, you can filter route information and modify route attributes to manage the communication between networks attached to the CEN.

You can configure route maps for different regional gateways in a CEN. Each regional gateway can be configured with a route map in the inbound direction and the outbound direction. Each route map is a set of conditional statements and executable statements. Route maps are sorted in ascending order of priority. When route maps are executed, the system first check whether the route map with the highest priority matches the conditional statements. The route map permit or deny routes. If a route is permitted, you can modify its attributes. For more information, see [Route map overview](reseller.en-US/User Guide/Routing policies/Route map overview.md#).

1.  Log on to the [CEN console](https://partners-intl.console.aliyun.com/#/cbn).
2.  In the left-side navigation pane, click **Instances**.
3.  On the Instances page, find the target CEN instance, and then click **Manage** in the **Actions** column.
4.  On the CEN page, click the **Route Maps** tab, and then click **Add Route Map**.
5.  On the Add Route Map page, set the parameters, and then click **OK**. The following table describes the parameters. 

    |Configuration|Description|
    |-------------|-----------|
    |**Priority**|The priority of the route map. A lower value indicates a higher priority. The priority of route maps in the same region and the same direction must be unique. When route maps are executed, the system first check whether the route map with the highest priority matches the conditional statements. Therefore, we recommend that you specify an appropriate priority for each route map.

 |
    |**Description**|Enter a description for the route map.|
    |**Region**|The region where the route map is applied.|
    |**Transmit Direction**|The direction of the route map.     -   Import to Regional Gateway: Routes are imported to the regional gateway of the CEN. For example, a route is published to the local regional gateway from a local network instance or from another region.
    -   Export from Regional Gateway: Routes are exported from the regional gateway of the CEN. For example, a route is published from a local regional gateway to another network instance in this region or to another regional gateway.
 |
    |**Match condition**|The match conditions of the route map. Click **+ Add Match Value** to add one or more matching conditions. For more information, see [Match conditions](reseller.en-US/User Guide/Routing policies/Route map overview.md#table_z6g_gjf_l3q).

 |
    |**Match Mode**|Select a match mode for the route map.     -   **Permit**: All routes that meet the match conditions are permitted.

If you set the match mode to Permit, the following actions are supported:

        -   **Preference**: Set the preference of the permitted route.
        -   **Community**: Set the Community attribute, which can be Additive or Replace.
    -   **Deny**: All routes that meet the match conditions are denied.

If you set the match mode to Deny, no other actions are supported.

 |
    |**Preference**|The preference of the associated next route map. Optional. Value range: 1 to 100.     -   If this parameter is not set, the current route map is not associated with the next route map.
    -   If this parameter is set to 1, the current route map is associated with the next route map.
    -   If this parameter is set to a value that is not 1, the preference of the associated route map must be greater than that of the current route map.
 Only route maps whose match mode is set to Permit will be checked whether they match route maps associated with preference after meeting all current match conditions.

 |



# Roll back the migration {#concept_827691 .concept}

This topic describes how to roll back your migration by modifying the routes.

Rollback solutions depend on the migration methods you have adopted. The available rollback solutions are as follows:

-   Migration with intermittent disconnections: Re-add the deleted static route of the peering connection. All the routes that are more detailed than or equals the re-added peering connection route are automatically deleted.
-   Smooth migration: Re-add the deleted detailed routes directly.

**Note:** If the migrated Virtual Border Router \(VBR\) is configured with BGP routes, you need to re-advertise the related CIDR blocks.


## Script: Get Availability Group Status, Listener, and Local Replica Role

**Description**:
This script retrieves detailed information about each Always On Availability Group on the local SQL Server instance. It includes the group name, listener DNS name, the name of the primary replica, and the **role of the local replica** (Primary, Secondary, or Resolving).

**What It Shows**:
- `AG Name`: Name of the Availability Group
- `Listener Name`: DNS name used by clients to connect to the AG
- `Primary Replica Server`: The replica currently acting as primary
- `Local Replica Role`: The role of the **current server** running the query (1 = Primary, 2 = Secondary, 3 = Resolving)

**Use Case**:
- Check if the local server is the primary or secondary
- Validate listener setup and primary routing
- Use in HA dashboards or AG health checks

**Requirements**:
- SQL Server 2012 or later
- Always On Availability Groups must be enabled
- `VIEW SERVER STATE` permission required

**Notes**:
- The `role` column shows the local server’s role:
  - `1`: Primary
  - `2`: Secondary
  - `3`: Resolving (transitioning state)

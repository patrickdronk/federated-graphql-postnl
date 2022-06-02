---
layout: center
clicks: 2
---

# Schema exposed by the Gateway 

```graphql {all|11}
# Business Locations of PostNL
type BusinessLocation {
    locationId: ID!
    blCode: String
    name: String
    shortName: String!
    position: Position
    locationType: String!
    organization: Organization
    type: String
    geofence: Geofence
}
```


<div class="abs-br m-6 flex gap-2">
<img 
        src="https://cdn.freebiesupply.com/logos/large/2x/postnl-3-logo-png-transparent.png"
        height="40"
        width="40"
    >
</div>
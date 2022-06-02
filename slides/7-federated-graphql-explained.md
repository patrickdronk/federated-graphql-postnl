---
layout: two-cols
clicks: 4
---

# Federated GraphQL

#### BusinessLocationService
```graphql {all|2}
# Business Locations of PostNL
type BusinessLocation @key(fields: "locationId") {
    locationId: ID!
    blCode: String
    name: String
    shortName: String!
    position: Position
    locationType: String!
    organization: Organization
    type: String
}
```

::right::

<div class="mt-14 ml-5">

#### GeofenceService

```graphql {all|2-7}
# Geofences for BusinessLocations
type Geofence {
    locationId: ID!
    polygon: Polygon!
    certainty: Float!
    point: [Float]!
}
```
<div class="mt-4">

```graphql {all|2-3|2-4}
# Enriching BusinessLocation, adding geofences to it
extend type BusinessLocation @key(fields: "locationId") {
    locationId: ID! @external
    geofence: Geofence
} 
```

</div>

</div>


<div class="abs-br m-6 flex gap-2">
<img 
        src="https://cdn.freebiesupply.com/logos/large/2x/postnl-3-logo-png-transparent.png"
        height="40"
        width="40"
    >
</div>
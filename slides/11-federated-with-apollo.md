---
clicks: 3
---

# Federated subgraph with Apollo

```javascript {all|5|all}
const typeDefsString = readFileSync('./location-registry-schema.graphql', 'utf-8');
const typeDefs = gql(typeDefsString);

const server = new ApolloServer({
    schema: buildSubgraphSchema([{ typeDefs, resolvers }]),
    dataSources: () => ({
        locationDataSource: new LocationsDatasource(),
        blsMappingDataSource: new BlsMappingDatasource(),
    }),
});

export const handler = server.createHandler();
```

<div class="mt-10" v-if="$slidev.nav.clicks >= 3">
As a bonus. The Apollo based server was 10% faster than the AppSync implementation
</div>


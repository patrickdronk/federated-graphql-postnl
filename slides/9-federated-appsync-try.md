---
---

# We tried it out
It didn't go well...

```javascript
export const handler = async (event: AppSyncResolverEvent<any>) => {
  let result: any = [];
  switch (event.info.parentTypeName) {
    case 'Product':
      switch (event.info.fieldName) {
        case 'createdBy':
          result = { email: 'support@apollographql.com', name: 'Apollo Studio Support', totalProductsCreated: 1337 };
          break;
      }
      break;
    case 'Query':
      switch (event.info.fieldName) {
        case 'product':
          if (event.arguments.id) result = products.find((p) => p.id === event.arguments.id);
          if (event.arguments.sku && event.arguments.package)
            result = products.find((p) => p.sku === event.arguments.sku && p.package === event.arguments.package);
          if (event.arguments.sku && event.arguments.variation && event.arguments.variation.id)
            result = products.find(
              (p) => p.sku === event.arguments.sku && p.variation.id === event.arguments.variation.id
            );
          break;
```

<div class="abs-br m-6 flex gap-2">
<img 
        src="https://cdn.freebiesupply.com/logos/large/2x/postnl-3-logo-png-transparent.png"
        height="40"
        width="40"
    >
</div>
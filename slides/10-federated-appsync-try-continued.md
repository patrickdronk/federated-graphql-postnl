---
---

# Continued #2
```javascript
case '_service':
          result = { sdl: process.env.SCHEMA };
          break;
        case '__typename':
          // Not sufficient : need capability to set extensions ...
          result = { ftv1: 'test' };
          break;
        case '_entities':
          const { representations } = event.arguments;
          const entities: any[] = [];
          for (const representation of representations as [any]) {
            const filteredProduct = products.find((p: any) => {
              for (const key of Object.keys(representation)) {
                if (typeof representation[key] != 'object' && key != '__typename' && p[key] != representation[key]) {
                  return false;
                } else if (typeof representation[key] == 'object') {
                  for (const subkey of Object.keys(representation[key])) {
                    if (
                      typeof representation[key][subkey] != 'object' &&
                      p[key][subkey] != representation[key][subkey]
                    ) {
                      return false;
};
```

---
clicks: 5
---

# GraphQL
<div>
<div grid="~ cols-2 gap-x-8">
<div v-if="$slidev.nav.clicks >= 1">

###### Compared to REST GraphQL

<v-clicks fade :at="1">

- No under or over-fetching of data
- Statically typed
- Errors will be exposed in the response body

</v-clicks>

<div class="mt-5" v-if="$slidev.nav.clicks >= 4">
Basic Query

```graphql
{
  allPersons {
    name
    posts {
      title
    }
  }
}
```
</div>
</div>
<div v-if="$slidev.nav.clicks>= 5">


Response

```json
{
  "allPersons": [
    { 
      "name": "Johnny",
      "posts": [
        {
          "title": "Some Magnificent Title"
        }
      ]
    },
    { 
      "name": "Sarah",
      "posts": [
        {
          "title": "The Philosopher's Graph"
        }
      ]
    }
  ]
}
```
</div>
</div>
</div>

<div class="abs-br m-6 flex gap-2">
<img 
        src="https://cdn.freebiesupply.com/logos/large/2x/postnl-3-logo-png-transparent.png"
        height="40"
        width="40"
    >
</div>
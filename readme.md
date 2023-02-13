
## Next 13 Features

## Turbo Pack
To run Turbopack change the dev command inside package.json 
```
"dev": "next dev --turbo",

```

<br> 

## Special files

- layout.js :
Contains the layout of the entire folder , it could contain navbar and footer . relative to the route

- page.js : equivalent to index.js

- loading.js : loading screen of current page.js

- error.js : Error screen current page.js

- head.js :file containing head tag .

 
<br> 

## Sever-side components
All components are default server-side components

<br> 

**ISR**

For dynamic route use caching

```
async function getData() {
    // revalidate cache: "60 seconds" 
    const res = await fetch('http://", { next : {revalidate : 60 } );  
     const data = await res.json();
}

```

<br> 

**SSR**

Get server side props
```
export const dynamicParams = true

//  fetching items at every request

async function getData() {
    const res = await fetch('http://", { cache: 'no-cache' });
     const data = await res.json();
}

// not found logic
```
<br> 

**SSG**
```
// static generation  

async function getData() {
    const res = await fetch('http://", { cache: 'forced-cache' });
     const data = await res.json();
}

// Get static static paths
export generateStaticParams() {
    const data = await getData()

    return data.map( (data) => {} )
}


function Component() {
    // use the fetched data
    const data = await getData()
}

```
<br> 

**Static page**

Get static side props

```
async function getData() {
    const res = await fetch('http://", { cache: 'forced-cache' });
     const data = await res.json();
}

```


## Client-side components

"use-client"


## instant data update

```
import {useRouter} from "next/navigation"

const router = useRouter()

async function submitForm() {

router.referesh

}

```


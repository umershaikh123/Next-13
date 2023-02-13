
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


This is a [Next.js 13](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

 
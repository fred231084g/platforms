# Simple Example

In this example, you'll learn how to build a simple multi-tenant platform on Vercel with custom domains support.

For context, here are some example pages:

- [subdomain-1.vercel.sh](https://subdomain-1.vercel.sh/) (subdomain)
- [subdomain-2.vercel.sh](https://subdomain-2.vercel.sh/) (subdomain)
- [subdomain-3.vercel.sh](https://subdomain-3.vercel.sh/) (subdomain)
- [custom-domain-1.com](https://custom-domain-1.com/) (custom domain, maps to [subdomain-1.vercel.sh](https://subdomain-1.vercel.sh/))

All of these generated sites are powered by ISR (no SSR at all) so they load pretty much instantly + the inter-page transitions are lightning fast.

The example above is generated based on the following mock database:

```
const mockDB = [
    {name: "Site 1", description: "Subdomain + custom domain", subdomain: "subdomain-1", customDomain: "custom-domain-1.com"},
    {name: "Site 2", description: "Subdomain only", subdomain: "subdomain-2", customDomain: null},
    {name: "Site 3", description: "Subdomain only", subdomain: "subdomain-3", customDomain: null},
]
```

When deploying your own clone of this example, you will need to replace the data fetching methods in `getStaticPaths` and `getStaticProps` with your own database of choice (BYOD, _Bring-Your-Own-Database_).

## How to Use

You can choose from one of the following two methods to use this repository:

### One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=next-example):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https://github.com/vercel-customer-feedback/edge-functions/tree/main/examples/hostname-rewrites&project-name=hostname-rewrites&repository-name=hostname-rewrites)

### Clone and Deploy

Download this repository via git:

```bash
git clone https://github.com/vercel-customer-feedback/edge-functions.git
```

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init) or [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/) to bootstrap the example:

```bash
npx create-next-app --example edge-middleware/examples/hostname-rewrites hostname-rewrites
# or
yarn create next-app --example edge-middleware/examples/hostname-rewrites hostname-rewrites
```

Deploy it to the cloud with [Vercel](https://vercel.com/new?utm_source=github&utm_medium=readme&utm_campaign=edge-middleware-eap) ([Documentation](https://nextjs.org/docs/deployment)).

> 💡 Do note that you will need to replace the `ROOT_URL` variable in the `.env.example` file with your domain of choice and add that domain as a wildcard domain your Vercel project.
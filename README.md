# NEAR (BOS)- BOSai ENCODE X NEAR HORIZON 2023
BOSai functions as a user's personal gateway into the blockchain ecosystem. It provides an interactive Chat Widget that guides users in navigating the BOS, answering their queries, and assisting in the initiation of blockchain interactions.

The platform comes with a built-in feature called Tinyauth, which enables the creation of Zero Balance accounts. With Tinyauth, users can securely store keys on their device and sign blockchain transactions without the need for an initial token balance. This feature simplifies the onboarding process, eliminating the barriers associated with account funding and key management.

To further enhance the user experience, Bonsai includes a relay system for meta transactions. This feature allows users to submit transactions on the blockchain without dealing with the underlying complexities, thus making their initial experiences with blockchain smooth and intuitive.

Incorporating the power of AI through the Vercel AI SDK and GPT Functions, Bonsai enables users to interact with the platform, create transactions, query data, and develop widgets simply by engaging in a conversation with the system.

In essence, BOSai nurtures the growth of users in the blockchain ecosystem, making the process of planting their roots and starting their journey as simple and intuitive as possible.

## BUILT

Blockchain Gateway: We've forked the near-discovery and created a Chat Widget on the Blockchain Operating System (BOS). This widget serves as a user-friendly interface, guiding users through the blockchain ecosystem.

Secure Authentication: We introduced BOSai Tinyauth, a minimalist implementation of FastAuth that securely stores keys on the user's device using WebAuthn. This enables users to create Zero Balance accounts and sign transactions without requiring an initial token balance.

Meta Transaction Relayer: To make the transaction submission process simpler, we built a relayer as a NextJS serverless function. This relayer allows users to submit meta transactions, abstracting the complex transaction details from the users.

Artificial Intelligence Integration: We've integrated the Vercel AI SDK along with GPT Functions into our platform. This integration enables BOSai to leverage AI technology, facilitating the development of user-friendly GPT plugins.

GPT Plugin Development: With the help of GPT plugins, users can perform various blockchain operations, such as creating transactions, querying data, and developing BOS widgets, through simple conversations with the system.

## Setup & Development

Initialize repo:

```
pnpm i
```

Start development version:

```
pnpm dev
```

## Local Component Development

1. Run an instance of a component server like [near/bos-loader](https://github.com/near/bos-loader) which serves component code in the following format

   ```json
   {
     "components": {
       "<component path 1>": {
         "code": "<component 1 code>"
       },
       "<component path 2>": {
         "code": "<component 2 code>"
       }
     }
   }
   ```

   this will be used as a `redirectMap` in `ViewPage`

2. Open the `/flags` route of your viewer and set the BOS Loader URL e.g. `http://127.0.0.1:3030`

Note: there is no hot reload, you must refresh the page to see component changes

## Local VM Development

> This section needs testing since switch to pnpm

If you need to make changes to the VM and test locally, you can easily link your local copy of the VM:

1. Clone the VM repo as a sibling of `near-discovery`:

```
git clone git@github.com:NearSocial/VM.git
```

Folder Structure:

```
/near-discovery
/VM
```

2. Run `pnpm link ../VM`

3. Any time you make changes to the `VM`, run `pnpm build` inside the `VM` project in order for the viewer project to pick up the changes

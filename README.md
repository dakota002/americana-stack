# Remix Americana Stack

Learn more about [Remix Stacks](https://remix.run/stacks).

To get started, run:

    npx create-remix@latest --template nasa-gcn/americana-stack

## What's in the stack

- Accessibility-first design system and CSS framework for United States government web sites with the [U.S. Web Design System (USWDS)](https://designsystem.digital.gov)
- USWDS widgets for React with [trussworks/react-uswds](https://github.com/trussworks/react-uswds.git)
- [AWS deployment](https://aws.com) with [Architect](https://arc.codes/)
- Production-ready [DynamoDB Database](https://aws.amazon.com/dynamodb/)
- DynamoDB access via [`arc.tables`](https://arc.codes/docs/en/reference/runtime-helpers/node.js#arc.tables)
- Code formatting with [Prettier](https://prettier.io)
- Linting with [ESLint](https://eslint.org)
- Static Types with [TypeScript](https://typescriptlang.org)
- Automated formatting, linting, and type checks on git commits with [husky](https://github.com/typicode/husky) and [lint-staged](https://github.com/okonet/lint-staged)

## Development

The following command will run two processes during development when using Architect as your server.

- Your Architect server sandbox
- The Remix development server

```sh
$ npm run dev
```

Your file changes are watched, and assets are rebuilt upon change.

Open up [http://localhost:3333](http://localhost:3333) and you should be ready to go!

## Deploying

Before you can deploy, you'll need to do some setup with AWS:

- First [install the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- Then [follow the Architect setup instructions](https://arc.codes/docs/en/guides/get-started/detailed-aws-setup).

If you make it through all of that, you're ready to deploy!

1. build the app for production:

   ```sh
   npm run build
   ```

2. Deploy with `arc`

   ```sh
   arc deploy production
   ```

You're in business!

## Styling

There are a variety of ways to add custom CSS styling.

### Theme customization - [`app/theme.scss`](https://github.com/nasa-gcn/americana-stack/blob/main/app/theme.scss)

You can customize the USWDS theme by adjusting any of the [USWDS settings](https://designsystem.digital.gov/documentation/settings/) or by adding custom [Sass](https://sass-lang.com) by editing the file [`app/theme.scss`](https://github.com/nasa-gcn/americana-stack/blob/main/app/theme.scss).

### Regular style sheets - `app/**/*.css`

You can add ordinary CSS stylesheets (file extension `.css`) anywhere in the [app](https://github.com/nasa-gcn/americana-stack/blob/main/app) directory and then [link them into the route modules where you need them](https://remix.run/docs/en/main/guides/styling#regular-stylesheets).

### CSS modules - `app/**/*.module.css`

You can add (file extension `.module.css`) anywhere in the [app](https://github.com/nasa-gcn/americana-stack/blob/main/app) directory and then [include them in any React component](https://remix.run/docs/en/main/guides/styling#css-modules).

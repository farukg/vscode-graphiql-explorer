# About this fork
 - fixes exploring graphql queries in ReasonML files when used with rescript-relay and adds same functionality for rescript for people who not yet fully switched to rescript
 - removed graphql language config in package.json because graphql.configuration.json was not present
 - it works on my machine, but i may have broke things :P 
 - i of course won't publish since i don't really know if i did everthing correctly, but vsix is checked in , you can use at your own risk
 - https://github.com/farukg/vscode-graphiql-explorer/blob/master/vscode-graphiql-explorer-1.3.1.vsix?raw=true
# vscode-graphiql-explorer

Use [GraphiQL](https://github.com/graphql/graphiql) + [OneGraph's](https://www.onegraph.com/) [GraphiQL Explorer](https://github.com/OneGraph/graphiql-explorer) to build your GraphQL operations, right from inside of VSCode.

![Demo](https://github.com/zth/vscode-graphiql-explorer/blob/master/images/vscode-graphiql-explorer.gif?raw=true)

## Features

- Explore your schema and edit + insert GraphQL operations using GraphiQL Explorer conveniently right from VSCode.
- Supports:
  - `graphql` and `gql` tags in JavaScript/TypeScript/Vue
  - `[%graphql]` and `[%relay]` nodes in ReasonML
  - Plain `.graphql` files
  - ...easy to add support for more languages and frameworks
- Explore your schema using GraphiQL right from VSCode.

## Setup

`vscode-graphiql-explorer` needs your introspected schema, either in a `.json` or a `.graphql` file. It tries to find your schema by looking in the workspace root for:

1. `schema.graphql`, `schema.json` or `graphql_schema.json`.
2. A `.graphqlconfig` file containing `schemaPath` pointing to your schema, like `{ "schemaPath": "/path/to/schema.graphql" }`.

If your schema is located somewhere other than the workspace root, please add and configure a `.graphqlconfig` file pointing to the schema as described above.

> **For large schemas, please prefer providing your schema in the SDL format (`.graphql`) rather than JSON**. That will make opening GraphiQL significantly faster.

If you don't have a schema file, you can create one by running `npx get-graphql-schema http://url/to/your/graphql/endpoint > schema.graphql` in your project root.

## Usage

Put your cursor in a GraphQL operation, activate "Code Actions" (the lightbulb that appears next to the code), and select `Edit GraphQL code in GraphiQL explorer`.

In addition to that, the extension adds 3 commands:

1. `Edit operation`, which does the same as described above, but through an explicit command. Use this with the cursor set in a tag (or full `.graphql` file) containing a GraphQL operation.
2. `Insert operation here`, which let you insert an operation into your source file via GraphiQL. Use this with the cursor set in an empty GraphQL tag, or in a `.graphql` file.
3. `Explore schema with GraphiQL`, which opens GraphiQL and let you explore your schema, without inserting or editing anything.

## Contributing

Is your favorite language/framework not supported? Check out [this link](https://github.com/zth/vscode-graphiql-explorer/issues/7#issuecomment-582071568) for instructions on how to PR support.

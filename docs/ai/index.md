---
id: overview
title: Overview
description: An overview of the AI features in Backstage.
---

Backstage provides a set of features that help AI coding assistants interact with your developer portal. These features fall into three areas: exposing Backstage functionality to AI clients through the Model Context Protocol (MCP), publishing curated guidance that teaches AI assistants how to perform Backstage tasks, and modeling AI-related resources in the Software Catalog.

## AI in the Software Catalog

Backstage provides several ways to represent AI-related resources as [entities in the Software Catalog](./ai-in-the-catalog.md). The [`AiResource`](./ai-in-the-catalog.md#airesource-entity-kind) entity kind models skills and governance rules as first-class entities with ownership, lifecycle, and dependency tracking. MCP servers can be represented using the [`API` kind with `type: mcp-server`](./ai-in-the-catalog.md#mcp-server-api-type), which captures transport endpoints through a `remotes` list.

## MCP Actions

The [MCP Actions Backend](./mcp-actions.md) plugin exposes actions registered with the [Actions Registry](../backend-system/core-services/actions-registry.md) as tools that MCP clients can call. This means AI coding assistants such as Claude, Cursor, and VS Code Copilot can query your Software Catalog, execute Software Templates, search across your portal, and more — all through a standardized protocol.

The MCP server uses the Streamable HTTP transport and supports OAuth authentication through [Client ID Metadata Documents (CIMD)](./mcp-actions.md#client-id-metadata-documents). See the [well-known actions](./well-known-actions.md) page for a reference of the actions that ship with Backstage.

## Published Skills

[Published skills](./skills.md) are self-contained guidance files that teach AI coding assistants how to perform common Backstage engineering tasks. Skills are published to a [well-known endpoint](https://backstage.io/.well-known/skills/) on `backstage.io` and can be installed into any repository with the [`skills.sh`](https://skills.sh/) tool.

Skills cover tasks such as migrating plugins to the new frontend system, instrumenting analytics events, and migrating from Material UI (MUI) to Backstage UI (BUI). See the [well-known skills](./well-known-skills.md) page for the full list.

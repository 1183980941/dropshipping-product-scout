# Dropshipping Product Scout

A Claude Code / Cowork plugin for dropshipping product research, powered by the CJdropshipping catalog. Search a human-curated product catalog, check real-time stock and variants, and estimate shipping costs — directly from your Claude conversation.

**Read-only and anonymous.** No account, no API key, and no OAuth required. The plugin connects to a hosted MCP server over Streamable HTTP; no credentials are stored on your machine.

## Tools

| Tool | What it does |
| --- | --- |
| `search_products` | Search the curated catalog by keyword or approved CJ SKU, with optional destination country and price filters. Returns up to 20 approved products with IDs, SPU, names, images, prices, categories, and stock signals. |
| `get_product_availability` | Check sell-state, real-time warehouse inventory, and approved variants for a given SPU or variant SKU. |
| `estimate_shipping` | Estimate delivery options for an approved variant: up to 20 carrier options with delivery times and USD freight/tax/clearance costs. |

## Installation

```
/plugin marketplace add 1183980941/dropshipping-product-scout
/plugin install dropshipping-product-scout
```

Or add the MCP server directly without the plugin:

```
claude mcp add --transport http product-scout https://mcp.youxiu.shop/mcp
```

## Example use cases

- "Find curated wireless earbuds under $15 that ship to the US, then estimate shipping for the best option."
- "Check whether SKU CJXXXXXXX is in stock and list its color variants."
- "Compare shipping options and costs to Germany for this variant."

## Safety & content policy

- The server only exposes a human-reviewed, general-audience product allowlist; unknown or restricted products fail closed.
- All inputs are strictly validated; all outputs are rebuilt against a fixed schema whitelist — no raw upstream data or tokens are passed through.
- Restricted-category search terms (adult, weapons, tobacco/vape, drugs, counterfeit) are rejected before any upstream request.

## Links

- Homepage: <https://mcp.youxiu.shop>
- Privacy policy: <https://mcp.youxiu.shop/privacy>
- Terms of service: <https://mcp.youxiu.shop/terms>
- Support: <https://mcp.youxiu.shop/support>

## License

MIT

# Aitrainingdatabroker.com ChatGPT plugin

Read-only ChatGPT app. Search the Aitrainingdatabroker.com blog, see the latest articles for sellers or buyers of AI training data, and read an article's opening with a link to the rest.

This repo is the plugin archive source (`plugin.json`, `mcp.json` and the two images) used to submit Aitrainingdatabroker.com to ChatGPT. The server itself is hosted by Aitrainingdatabroker.com and needs no account and no API key.

## What is a ChatGPT plugin?

A ChatGPT plugin (also called an app) lets ChatGPT call an outside service while it answers you. Here ChatGPT calls the Aitrainingdatabroker.com MCP server, a read-only endpoint, and shows you the result with a link back to the full article on the site.

## About Aitrainingdatabroker.com

AI Training Data Broker is an independent broker for company data deals with AI labs. Companies with 20 or more people sell or license their operational data to AI labs for training, with third-party de-identification and counsel-reviewed contracts; labs and model teams source licensed, de-identified workflow data. Its blog answers the questions both sides ask. Visit it at https://aitrainingdatabroker.com.

## Endpoint

```
https://aitrainingdatabroker.com/api/mcp
```

Model Context Protocol over Streamable HTTP, read-only, no authentication.

## Files

- `plugin.json`: name, description, prompts, links to the privacy policy and terms.
- `mcp.json`: points ChatGPT at the endpoint above.
- `assets/icon.png`, `assets/logo.png`: icons.

## Build the archive

Put the files at the ZIP root, not inside a folder:

```
python -c "import zipfile;z=zipfile.ZipFile('aitrainingdatabroker-plugin.zip','w',zipfile.ZIP_DEFLATED);[z.write(f,f) for f in ['plugin.json','mcp.json','assets/icon.png','assets/logo.png']];z.close()"
```

Bump `version` in `plugin.json` for any metadata change. Server-side changes need no new archive.

## More from Aitrainingdatabroker.com

- Website: https://aitrainingdatabroker.com
- Blog: https://aitrainingdatabroker.com/blog/
- Developer docs for Claude: https://aitrainingdatabroker.com/docs/claude/
- Developer docs for ChatGPT: https://aitrainingdatabroker.com/docs/chatgpt/
- Claude connector: https://github.com/ExpatsListORG/aitrainingdatabroker-claude-connector
- Claude skill: https://github.com/ExpatsListORG/aitrainingdatabroker.com
- Privacy policy: https://aitrainingdatabroker.com/privacy/
- Terms of service: https://aitrainingdatabroker.com/terms/
- Contact: https://aitrainingdatabroker.com/contact/

## License

MIT. See `LICENSE`.

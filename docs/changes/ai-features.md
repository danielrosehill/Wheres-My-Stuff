# AI Features & MCP

## AI Integration Philosophy

I thought it was vital to integrate support for AI and MCP. An emerging best practice seems to be integrating MCP servers directly into self-hosted or other web applications, making it easier for users who don't have to deploy an MCP server alongside the tool.

I created an MCP for Homebox a couple of months ago and integrated the core functionalities into a built-in MCP which provides its endpoint within the AI features settings page.

## OpenRouter Integration

As the core driver of AI functionality, I wanted to use OpenRouter because it makes it easy to swap out models. Google Gemini Flash and Lite struck me as the most versatile and obvious LLM choice, given its cost-effectiveness and multimodal support—particularly useful in the inventory use case where images can be leveraged to extract data via workflows that might classically have been done by dedicated OCR tools.

## Selective AI Features

I'm adding AI functions selectively where they make sense and with caution. The general pattern is using known data to infer missing data that would be tedious to add manually but is helpful to have in the system.

As a simple example, if you know the manufacturer, have a photo, and have the part number, you can infer with a good degree of accuracy:

- The product spec sheet
- The regional PN

<figure class="screenshot" markdown>
  ![Item Details](../screenshots/v1/item-management/item-details.png)
  <figcaption>Item details with AI-enhanced fields</figcaption>
</figure>

## Built-in MCP Server

The built-in MCP server provides:

- Asset retrieval and search
- Location management
- Inventory queries
- Integration with AI assistants and agents

Configuration is available in the AI features settings page.

# Changelog

Changes from upstream [Homebox](https://github.com/sysadminsmedia/homebox) as of the fork date: **13 December 2025**.

---

## Semantic Search

I love Homebox! It's been one of the few pieces of open source software that has measurably improved my life and has even drawn praise from non-techie friends who would usually regard my tech projects as strange.

The only long-standing frustration I had with it was poor retrieval—a significant limitation for an inventory system. The most important change implemented was semantic search. The addition of embeddings and vectors to support retrieval from AI tools takes this a step further.

## Streamlined Keyword / Asset ID Lookup

The current Homebox implementation uses hashtag prepending for asset lookup and keywords otherwise. I figured simple rule-based logic could distinguish between these two lookup patterns: queries containing only numbers can be understood as asset ID lookups, distinguishing them from text queries that happen to include numbers.

Most of my Homebox use consists of typing things into it one-handed on a phone to find a cable. Most of the subtle UI changes are designed to support easy use in these scrappy conditions.

## Lookup Tables & Data Types

Because most of my Homebox use involves inventorying technical items, I wanted to add standard lookup fields for common things like cables. Lookup fields were defined in the database and integrated as dropdown options on the frontend.

## Vendors & Manufacturers

I put some thought into the best way to minimise the limitations of manual text entry where that might pose challenges to data integrity.

One such limitation was the custom fields implementation, which doesn't support lookup in the UI. This makes it easy to create repetitive duplicate fields, which in turn makes filtering on them difficult.

Custom fields are now defined in settings to avoid this problem. If a custom field is missing and needs to be created, the intended workflow is that the user creates it in settings first, then uses that field on items. While slightly less flexible, this should prevent data inconsistency.

Additionally, I added tables for vendors and manufacturers to support filtering on these as reusable entities.

## Location Photos

One Homebox limitation I wanted to work around was adding photographs for locations. A photograph of a box is unlikely to win any creative awards, but it's useful when you have a lot of them.

More importantly, adding location photos supports the storage flow I use (and I imagine many others do too):

- Locations map onto rooms
- Within those rooms there are boxes/containers
- Within those boxes there are assets

## Parent & Child Asset Decoupling

I wasn't able to figure out the UI functionality to decouple parent and child assets, so I added this.

## AI Features & MCP

I thought it was vital to integrate support for AI and MCP. An emerging best practice seems to be integrating MCP servers directly into self-hosted or other web applications, making it easier for users who don't have to deploy an MCP server alongside the tool.

I created an MCP for Homebox a couple of months ago and integrated the core functionalities into a built-in MCP which provides its endpoint within the AI features settings page.

As the core driver of AI functionality, I wanted to use OpenRouter because it makes it easy to swap out models. Google Gemini Flash and Lite struck me as the most versatile and obvious LLM choice, given its cost-effectiveness and multimodal support—particularly useful in the inventory use case where images can be leveraged to extract data via workflows that might classically have been done by dedicated OCR tools.

I'm adding AI functions selectively where they make sense and with caution. The general pattern is using known data to infer missing data that would be tedious to add manually but is helpful to have in the system.

As a simple example, if you know the manufacturer, have a photo, and have the part number, you can infer with a good degree of accuracy:
- The product spec sheet
- The regional PN

## Spec Sheet Tab

One of my primary uses for Homebox is that it makes it easy to keep data together from different sources—things like warranty documents and spec sheets.

These come in different formats: some are PNG, others are PDF. I added "Specs" as a new tab at the asset page level to allow users to gather spec sheets in one specific place. Photos can still be used for product marketing images.

Defining the spec sheet is also useful for AI enhancements and workflows. I've been able to use workflows like finding deprecated technology simply by retrieving the spec sheet from the product number and manufacturer.

## Thumbnail & Loading Time Optimisations

Inventory photos don't need to be high resolution to be clearly legible.

Over the course of using Homebox, I've created backend scripts to run bulk compression tasks on images. However, if your image store is in the thousands or tens of thousands, this can be a lengthy and computationally heavy process. You can run a backfill on existing photos, but prevention is better than cure.

To support faster loading of list pages, I added a micro-thumbnail size of 200 pixels—sufficient for clear display on search and list pages. Post-upload optimisation to compress images is also added. Combined with indexing at the database level, this should provide a faster user experience.

## NFC Support

Implementing NFC support at the desktop level is challenging. There are ways to connect browser-based tools with local processes, but I thought it was needless complication.

Instead, the NFC integration only displays on mobile devices. I added a setting to distinguish between write, and write-and-lock operations. I personally use write-and-lock, which permanently locks tags to prevent accidental rewriting. But for flexibility, I added a simple write feature as well. Write-and-password-protect is a more versatile option and could be added. The feature works nicely on Android devices.

## Favourite Items

I find that I look up a small number of items frequently, and most very infrequently. To support easily finding your most looked-up items, I added a favourites entity and frontend elements to easily toggle these on and off using standard star iconography.

## API Key Management

Homebox has a good API that is defined with a proper schema, but generated tokens created manually are short-lived. I wanted to add a dedicated API key management utility to support integration with AI tools.

## Currency

Homebox allows users to define a currency. Valuing items is potentially very useful for insurance appraisals.

However, practically speaking, when ordering things from the internet many people use multiple currencies. Recording the original currency alongside the value is an important concept because it allows valuations to be centralised on a standard currency with up-to-date exchange rates.

As a first step towards supporting this kind of implementation, the revised format allows users to define their primary currency while supporting currency as a label in fields with financial values.

## Menu Consolidation

I wanted to keep the menu as easy to use as possible, so I'm trying to find ways to integrate different pages and divide the menu with dropdown sub-menus where sensible. I also added a dedicated assets page, which previously was only accessible when using the search function.

---

## Implementation Status

Like most contributors to and users of the project, I have time to make updates to my instance periodically and in bursts. Not all features are fully integrated yet.

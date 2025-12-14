# Data Structure Improvements

## Lookup Tables & Data Types

Because most of my Homebox use involves inventorying technical items, I wanted to add standard lookup fields for common things like cables. Lookup fields were defined in the database and integrated as dropdown options on the frontend.

## Vendors & Manufacturers

I put some thought into the best way to minimise the limitations of manual text entry where that might pose challenges to data integrity.

One such limitation was the custom fields implementation, which doesn't support lookup in the UI. This makes it easy to create repetitive duplicate fields, which in turn makes filtering on them difficult.

Custom fields are now defined in settings to avoid this problem. If a custom field is missing and needs to be created, the intended workflow is that the user creates it in settings first, then uses that field on items. While slightly less flexible, this should prevent data inconsistency.

Additionally, I added tables for vendors and manufacturers to support filtering on these as reusable entities.

<figure class="screenshot" markdown>
  ![Add Item](../screenshots/v1/item-management/add-item.png)
  <figcaption>Add item form with vendor/manufacturer fields</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Edit Item](../screenshots/v1/item-management/edit-item.png)
  <figcaption>Edit item with structured data fields</figcaption>
</figure>

## Currency Support

Homebox allows users to define a currency. Valuing items is potentially very useful for insurance appraisals.

However, practically speaking, when ordering things from the internet many people use multiple currencies. Recording the original currency alongside the value is an important concept because it allows valuations to be centralised on a standard currency with up-to-date exchange rates.

As a first step towards supporting this kind of implementation, the revised format allows users to define their primary currency while supporting currency as a label in fields with financial values.

<figure class="screenshot" markdown>
  ![Item Details](../screenshots/v1/item-management/item-details.png)
  <figcaption>Item details with currency and value fields</figcaption>
</figure>

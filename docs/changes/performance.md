# Performance Optimisations

## Thumbnail & Loading Time Optimisations

Inventory photos don't need to be high resolution to be clearly legible.

Over the course of using Homebox, I've created backend scripts to run bulk compression tasks on images. However, if your image store is in the thousands or tens of thousands, this can be a lengthy and computationally heavy process. You can run a backfill on existing photos, but prevention is better than cure.

To support faster loading of list pages, I added a micro-thumbnail size of 200 pixels—sufficient for clear display on search and list pages. Post-upload optimisation to compress images is also added. Combined with indexing at the database level, this should provide a faster user experience.

<figure class="screenshot" markdown>
  ![View All Items](../screenshots/v1/item-management/view-all-items.png)
  <figcaption>Optimised list view with micro-thumbnails</figcaption>
</figure>

## Database Indexing

Strategic indexing has been added to improve query performance, particularly for:

- Asset lookups by ID
- Keyword searches
- Location-based filtering
- Vendor/manufacturer filtering

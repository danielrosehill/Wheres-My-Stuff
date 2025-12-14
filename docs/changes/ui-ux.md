# UI & UX Enhancements

## Location Photos

One Homebox limitation I wanted to work around was adding photographs for locations. A photograph of a box is unlikely to win any creative awards, but it's useful when you have a lot of them.

More importantly, adding location photos supports the storage flow I use (and I imagine many others do too):

- Locations map onto rooms
- Within those rooms there are boxes/containers
- Within those boxes there are assets

<figure class="screenshot" markdown>
  ![Add Item With Image](../screenshots/v1/item-management/add-item-with-image.png)
  <figcaption>Adding items with location photos</figcaption>
</figure>

## Spec Sheet Tab

One of my primary uses for Homebox is that it makes it easy to keep data together from different sources—things like warranty documents and spec sheets.

These come in different formats: some are PNG, others are PDF. I added "Specs" as a new tab at the asset page level to allow users to gather spec sheets in one specific place. Photos can still be used for product marketing images.

Defining the spec sheet is also useful for AI enhancements and workflows. I've been able to use workflows like finding deprecated technology simply by retrieving the spec sheet from the product number and manufacturer.

<figure class="screenshot" markdown>
  ![Item Details](../screenshots/v1/item-management/item-details.png)
  <figcaption>Item details page with specs tab</figcaption>
</figure>

## Parent & Child Asset Decoupling

I wasn't able to figure out the UI functionality to decouple parent and child assets, so I added this.

<figure class="screenshot" markdown>
  ![Delete Item](../screenshots/v1/item-management/delete-item.png)
  <figcaption>Item management with parent/child decoupling options</figcaption>
</figure>

## Favourite Items

I find that I look up a small number of items frequently, and most very infrequently. To support easily finding your most looked-up items, I added a favourites entity and frontend elements to easily toggle these on and off using standard star iconography.

<figure class="screenshot" markdown>
  ![View All Items](../screenshots/v1/item-management/view-all-items.png)
  <figcaption>Items list with favourite toggle</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![My Items](../screenshots/v1/user-profile/my-items.png)
  <figcaption>My items view with favourites</figcaption>
</figure>

## Menu Consolidation

I wanted to keep the menu as easy to use as possible, so I'm trying to find ways to integrate different pages and divide the menu with dropdown sub-menus where sensible. I also added a dedicated assets page, which previously was only accessible when using the search function.

<figure class="screenshot" markdown>
  ![View Profile](../screenshots/v1/user-profile/view-profile.png)
  <figcaption>Streamlined profile view</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Edit Profile](../screenshots/v1/user-profile/edit-profile.png)
  <figcaption>Edit profile interface</figcaption>
</figure>

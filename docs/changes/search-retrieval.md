# Search & Retrieval

## Semantic Search

I love Homebox! It's been one of the few pieces of open source software that has measurably improved my life and has even drawn praise from non-techie friends who would usually regard my tech projects as strange.

The only long-standing frustration I had with it was poor retrieval—a significant limitation for an inventory system. The most important change implemented was semantic search. The addition of embeddings and vectors to support retrieval from AI tools takes this a step further.

<figure class="screenshot" markdown>
  ![Search by Keyword](../screenshots/v1/search-and-filter/search-by-keyword.png)
  <figcaption>Keyword search interface</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Advanced Search](../screenshots/v1/search-and-filter/advanced-search.png)
  <figcaption>Advanced search with semantic capabilities</figcaption>
</figure>

## Streamlined Keyword / Asset ID Lookup

The current Homebox implementation uses hashtag prepending for asset lookup and keywords otherwise. I figured simple rule-based logic could distinguish between these two lookup patterns: queries containing only numbers can be understood as asset ID lookups, distinguishing them from text queries that happen to include numbers.

Most of my Homebox use consists of typing things into it one-handed on a phone to find a cable. Most of the subtle UI changes are designed to support easy use in these scrappy conditions.

<figure class="screenshot" markdown>
  ![Filter by Category](../screenshots/v1/search-and-filter/filter-by-category.png)
  <figcaption>Filter results by category</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Sort Results](../screenshots/v1/search-and-filter/sort-results.png)
  <figcaption>Sort and organize search results</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Location-Based Search](../screenshots/v1/search-and-filter/location-based-search.png)
  <figcaption>Location-based search for quick lookups</figcaption>
</figure>

## Saved Searches & History

<figure class="screenshot" markdown>
  ![Saved Searches](../screenshots/v1/search-and-filter/saved-searches.png)
  <figcaption>Save frequently-used searches</figcaption>
</figure>

<figure class="screenshot" markdown>
  ![Search History](../screenshots/v1/search-and-filter/search-history.png)
  <figcaption>View search history</figcaption>
</figure>

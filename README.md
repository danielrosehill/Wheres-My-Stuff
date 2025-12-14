# Where's My Stuff?

A customised fork of [Homebox](https://github.com/sysadminsmedia/homebox), the home inventory system.

## About

Where's My Stuff (WMS) is an entirely vibe-coded fork of Homebox, undertaken by Claude under my supervision. Like all vibe-coded projects, WMS is offered on a "might work" basis.

When/if I have something stable-ish to share, I will do so here.

## Why Fork?

Homebox has a dedicated team of contributors. I wanted to add some niche features that I doubted would interest the broader user community. In the interest of streamlining the codebase, I also removed some features I didn't need—most significantly, replacing barcode/label support with NFC.

Creating a derivative fork for my own use made more sense than sending back PRs of dubious code quality. Vibe coding is scrappy! The main project may wish to integrate any of these features, or not.

## Summary of Changes

*Forked from Homebox on 13 December 2025. See [CHANGELOG.md](CHANGELOG.md) for detailed implementation notes.*

### Search & Retrieval
- **Semantic search** with embeddings and vector support for AI-powered retrieval
- **Streamlined asset lookup** — numeric queries treated as asset IDs, text queries as keyword searches

### Data Structure Improvements
- **Lookup tables** for common technical items (cables, connectors, etc.)
- **Vendors & manufacturers** as reusable entities with filtering support
- **Custom field management** via settings to prevent duplicate/inconsistent entries
- **Multi-currency support** — record original purchase currency alongside value

### UI & UX Enhancements
- **Location photos** — photograph storage locations (boxes, shelves, etc.)
- **Favourites** — star frequently-accessed items for quick lookup
- **Spec sheet tab** — dedicated place for spec sheets and product documentation
- **Menu consolidation** — simplified navigation with dropdown sub-menus
- **Dedicated assets page** — direct access without requiring search

### Performance
- **Thumbnail optimisation** — 200px micro-thumbnails for faster list loading
- **Post-upload compression** — automatic image optimisation
- **Database indexing** improvements

### Integrations
- **NFC support** — write/lock NFC tags on mobile devices (replaces barcode/label system)
- **Built-in MCP server** — Model Context Protocol endpoint for AI tool integration
- **OpenRouter integration** — AI features powered by configurable LLMs (default: Google Gemini Flash)
- **API key management** — dedicated utility for long-lived API keys

### Other
- **Parent/child asset decoupling** — UI to unlink related assets

## Implementation Status

Features are being integrated periodically. Not all are fully complete yet.

## Upstream

This fork tracks [sysadminsmedia/homebox](https://github.com/sysadminsmedia/homebox). Features may diverge from upstream as both projects evolve.

## Screenshots

### User Authentication
- Login Screen: ![Login Screen](screenshots/v1/user-authentication/login-screen.png)
- Registration Screen: ![Registration Screen](screenshots/v1/user-authentication/registration-screen.png)
- Forgot Password Screen: ![Forgot Password Screen](screenshots/v1/user-authentication/forgot-password-screen.png)
- Social Login: ![Social Login](screenshots/v1/user-authentication/social-login.png)
- 2FA Setup: ![2FA Setup](screenshots/v1/user-authentication/2fa-setup.png)

### Item Management
- Add Item: ![Add Item](screenshots/v1/item-management/add-item.png)
- Add Item With Image: ![Add Item With Image](screenshots/v1/item-management/add-item-with-image.png)
- Edit Item: ![Edit Item](screenshots/v1/item-management/edit-item.png)
- Delete Item: ![Delete Item](screenshots/v1/item-management/delete-item.png)
- Item Details: ![Item Details](screenshots/v1/item-management/item-details.png)
- View All Items: ![View All Items](screenshots/v1/item-management/view-all-items.png)
- Mark as Found: ![Mark as Found](screenshots/v1/item-management/mark-as-found.png)
- Request Item: ![Request Item](screenshots/v1/item-management/request-item.png)
- Lend Item: ![Lend Item](screenshots/v1/item-management/lend-item.png)

### Search and Filter
- Search by Keyword: ![Search by Keyword](screenshots/v1/search-and-filter/search-by-keyword.png)
- Filter by Category: ![Filter by Category](screenshots/v1/search-and-filter/filter-by-category.png)
- Sort Results: ![Sort Results](screenshots/v1/search-and-filter/sort-results.png)
- Advanced Search: ![Advanced Search](screenshots/v1/search-and-filter/advanced-search.png)
- Location-Based Search: ![Location-Based Search](screenshots/v1/search-and-filter/location-based-search.png)
- Saved Searches: ![Saved Searches](screenshots/v1/search-and-filter/saved-searches.png)
- Search History: ![Search History](screenshots/v1/search-and-filter/search-history.png)

### User Profile
- View Profile: ![View Profile](screenshots/v1/user-profile/view-profile.png)
- Edit Profile: ![Edit Profile](screenshots/v1/user-profile/edit-profile.png)
- Change Password: ![Change Password](screenshots/v1/user-profile/change-password.png)
- My Items: ![My Items](screenshots/v1/user-profile/my-items.png)
- Notification Settings: ![Notification Settings](screenshots/v1/user-profile/notification-settings.png)
- Privacy Settings: ![Privacy Settings](screenshots/v1/user-profile/privacy-settings.png)


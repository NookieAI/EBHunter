# Changelog

## [v0.2.2] - 2026-09-05

### Fixed
- Removed "View Product" button that linked to external website
- Sort by price now uses effective sale price instead of original price
- Ctrl+Shift+C no longer blocked — text can be copied from modal
- Right-click context menu now works on selectable text (title, description)
- Cache directory now uses platform-appropriate path on macOS and Linux
- Animation delay no longer grows unbounded for large result sets (capped at 0.6s)
- localStorage reads wrapped in try-catch to prevent crashes on corrupt data
- Cleaned up dead code (unused productUrl references)

### Improved
- Price tracking batched into single write per render instead of per-card
- Price history pruned at 1000 entries to prevent unbounded localStorage growth
- Pagination added — games and deals load 60 at a time with "Load More" button
- Loading spinner shown during initial catalog fetch
- Broken images now show a gamepad fallback icon instead of empty boxes

## [v0.2.1] - 2026-08-26

### Security
- Catalog data encrypted at rest with AES-256-GCM; CDN serves ciphertext only
- CDN fallback URL corrected to match actual R2 object key

## [v0.2.0] - 2026-08-22

### Added
- Game descriptions with formatted text display
- Screenshot gallery with full-screen lightbox viewer (keyboard navigation, counter)
- All images and metadata served from CDN — zero external dependencies at runtime
- Price drop notifications via toast alerts
- Price history tracking across sessions
- Surprise Me button for random game discovery
- Recently viewed games section on home screen
- Home screen highlight cards (deals count, catalog size, pre-orders, cheapest new)
- Condition filter (new / pre-owned)
- Price range filter
- Sort by relevance, price, name, or release date

### Security
- Devtools access blocked in release builds
- Right-click context menu disabled
- Text selection limited to copyable content only
- Image dragging disabled
- CSP locked to self + CDN only

### Changed
- Catalog auto-refreshes every 4 hours with stale fallback
- Gallery thumbnails open lightbox instead of replacing cover image

## [v0.1.0] - 2026-08-21

### Added
- Initial release
- Browse and search across all Australian EB Games stores
- Platform filters (PS5, PS4, Switch, Switch 2, Xbox, PC)
- Game cards with cover art, pricing, badges, and ratings
- Product detail modal with availability info
- Watchlist with localStorage persistence
- View Product button to open EB Games product page

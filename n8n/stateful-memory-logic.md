# Stateful Memory Logic for Web Scrapers

To optimize API consumption and prevent redundant processing, I implemented a stateful memory system within n8n workflows. This ensures that the engine only processes unique URLs within a sliding 4-hour window.

### Technical Implementation
The system uses a JavaScript-based filtering node to compare incoming URLs against a local or database-backed state.

```javascript
// Example logic used in the Function Node
const processedUrls = await $getStoredData(); // Hypothetical storage call
return items.filter(item => !processedUrls.includes(item.json.url));

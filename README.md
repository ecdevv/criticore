<p align="center">
  <h1 align="center">CritiCore - Review Aggregator of OpenCritic and Steam Reviews</h1>
  <p align="center">Video game critic aggregator for PC games using Steam and OpenCritic APIs.</p>
</p>

<p align="center">
  <a href="https://criticore.vercel.app" target="_blank" rel="noopener noreferrer" align="center">
    <img src="/public/criticore_preview.webp" alt="Site Preview"/>
  </a>
</p>

CritiCore is a personal web project designed to enhance my development skills by presenting API endpoint data in an intuitive and visually engaging way. The platform focuses on creating a seamless, user-friendly experience, allowing me to practice building features that make complex data accessible and easy to navigate. This project serves as a hands-on opportunity to refine my abilities in web development, API integration, and user interface design.

## Tools & Frameworks

- **Core:** HTML, Tailwind CSS, TypeScript
- **Framework:** Next.js, React
- **Key Libraries:** `sharp`, `damerau-levenshtein`, `date-fns`, `ioredis`, `steamgriddb`, `cheerio`

## Features

- **Dynamic Game Pages:** Fetches detailed game data to render responsive, interactive game pages
- **Smart Search:** Intuitive dynamic search system with Steam integration (limited OpenCritic API support)
- **Responsive Design:** Fully adaptive layout optimized for viewing across various devices
- **Performance Optimization:** Implements dynamically generated blur placeholders to improve perceived load speeds and visual feedback
- **Efficient Caching:** Utilizes Upstash/Redis for data caching and Next.js revalidation for optimized performance
- **SEO Optimization:** Implements metadata, sitemaps, and OpenGraph tags for better search engine visibility

## Installation

```bash
# 1. Clone the repository:
git clone https://github.com/ecdevv/criticore.git

# 2. Navigate into the repository:
cd criticore

# 3. Copy the example .env file and set up environment variables where its empty:
cp .env.example .env

# 4. Install dependencies:
npm install

# 5. Run the app:
npm start or npm run dev
```

## Notes/Potential Improvements/Known Issues

### Notes

- Built entirely from scratch without pre-built templates or boilerplates
- Limited external libraries to `sharp` (blur data generation), `date-fns` (date formatting), `damerau-levenshtein` (fuzzy search), `ioredis` (caching), `steamgriddb` (image fallbacks), and `cheerio` (lightweight scraping)
- Minimized web scraping by only using it for search functionality to bypass slow Steam AppList/AppIndex queries and capture unlisted/soon-to-release titles
- OpenCritic official API requests use cache: 'force-cache' to mitigate rate limits, though exact cache expiration timing remains undefined
- Upstash free tier is capped at 10k commands/day. Blur data URL generation consumes a high volume of commands, making the current limit a significant bottleneck
- Live deployment performance is noticeably slower than local development due to execution and resource limits on Vercel and Upstash free tiers
- Loading and Not-found pages are incomplete

### Potential Improvements

- Refine overall visual design, spacing, and component aesthetics for a more polished presentation
- Introduce additional game metadata displays, comparison tools, or related features
- Implement robust data validation and graceful error boundaries for API failures, cache timeouts, and invalid responses
- Implement smarter caching strategies (e.g., TTL management, command batching, or tiered storage) to stay within Upstash limits

## Credits

### Data Sources
  - [OpenCritic](https://rapidapi.com/opencritic-opencritic-default/api/opencritic-api): For game metadata, ratings, reviews, media elements, and related data.
  - [Steam](https://steamcommunity.com/dev): For game metadata, ratings, reviews, media elements, and related data.
  - [SteamGridDB](https://www.steamgriddb.com/api/v2): For media elements.

### Images
  - ocLogo.svg: OpenCritic Inc, Public domain, via Wikimedia Commons
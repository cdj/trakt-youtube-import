# trakt-youtube-import
 Import Google Takeout YouTube history and selectively sync to Trakt

## Flow
1. Programmatically import Takeout
    - Grab in segments if we already have the older data?
2. Process file
    - Pull out stuff which can be mapped to Trakt
        - Is there a mapping anywhere?
        - Content types
            - Movies and Shows for purchase/rent in [storefront](https://www.youtube.com/feed/storefront)
            - YouTube shows (e.g. Hot Ones)
            - Movies (shorts, unofficial uploads)
        - Custom mapping? Channel + regex (+ playlist?)
            - store in spreadsheet like [Netflix sync extension](https://github.com/tegon/traktflix) [doc](https://docs.google.com/spreadsheets/d/1Yq9rnpszwh2XFVllLkNelaFeu8FY0lldd91ce7JVZPk/edit?usp=sharing)
            - Publish Date to match against Trakt air date

    - Identify duplicates
        - multiple plays on YouTube
        - multiple plays on Trakt
        - cluster by datetime for duplicate data near each other (rounding errors, start and continue next day...)

3. Display results in UI
4. Settings
    - Time range to cluster (i.e. consider duplicate if within 1 week)
5. Select data to sync
    - Auto consolidate clusters
        - Pure duplicates: same time (rounded?)
        - Preferred order of data source
        - Preferred date: earliest, latest, middle, mean, median
    - Push updates to Trakt
    - Delete existing Trakt data if it was marked as duplicate
6. Selectively delete bad data
    - link to delete from YouTube history (is there an API?)

## Potential Features
- Sync Thumbs-Up data from YouTube API for Trakt rating
- Sync YouTube playlist to Trakt playlist
- Scrape from webpage
    - [Google myactivity](https://myactivity.google.com/product/youtube?hl=en&utm_medium=web&utm_source=youtube&restrict=youtube)
	- [YouTube history page](https://www.youtube.com/feed/history)
        - Watch % by progress bar?

## Similar Projects
- [Netflix sync extension](https://github.com/tegon/traktflix)
- [PlexTraktSync](https://github.com/Taxel/PlexTraktSync)

## Changes
 - 2022-10-18 Project start



# trakt-youtube-import

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

# Ido Mizrachi Learning Path (2026)

## Current state
I'm a senior software engineer, with deep knowledge in iOS development, general software (mostly backend) development, relational databases and system architecture.

## Learning Journal
I am documenting my progress in the [`journal/`](./journal) directory.
- [Template](./journal/_template.md)

## Goals for next year


### Mobile

#### iOS
[ ] Learn SwiftUI - since more of my knowledge is in UIKit, I want to close this gap and be able to build iOS apps with SwiftUI.
    - **Project: Settings Clone**: Rebuild the iOS Settings app UI to understand Lists, Navigation, and State.
    - **Project: Crypto Ticker**: Fetch live prices, use Charts to visualize history (Swift Charts), and update UI reactively.
[ ] Learn SwiftData
    - **Project: Offline-First Todo**: Build a task manager that syncs iCloud but works offline, handling relationships (Categories <-> Tasks) and migrations.
    - **Project: Expense Insights**: A budget app focusing on complex data queries.
        - Learn `@Query` with dynamic `Predicate` (filter by date range/category).
        - Perform efficient aggregations (summing totals) directly from the model context.
        - Visualize spending trends using Swift Charts bound to SwiftData models.

#### Android
[ ] Kotlin Fundamentals - Focus on differences from Swift (Data classes, Coroutines, etc).
    - **Project: CLI Note Taker**: A simple command-line tool to add, list, and delete notes to a file, using Kotlin's IO and data classes.
[ ] Jetpack Compose - Modern, declarative UI for Android (conceptual map to SwiftUI).
    - **Project: Movie Browser**: Fetch data from TMDB API, display a grid of posters, and a detailed view with animations.
[ ] Modern Android Architecture - MVVM with ViewModel, LiveData/Flow, and Dependency Injection (Hilt/Koin).
    - **Project: Weather App**: Implement location services, API repository pattern, and reactive UI updates based on weather changes.

### Frontend (web)

[ ] Css - Flexbox mastering
[ ] React Core - Deep dive into Hooks (useEffect, useMemo, useCallback), Context API, and Virtual DOM.
    - **Project: Dashboard Widget**: A configurable dashboard where users can add/remove/resize widgets (weather, clock, stocks), requiring complex state management.
[ ] Next.js - App Router, Server Components, and API routes.
    - **Project: Personal Dev Blog (The Journal Website)**
        - **Goal**: Build a static site to publish the `journal/` markdown files, hosted free on GitHub Pages.
        - **Frontend Tasks**:
            - [ ] **UI Architecture**: Layout with Sidebar/Header, Responsive Design, and Typography for long-form reading.
            - [ ] **MDX Rendering**: Use `next-mdx-remote` or `contentlayer` to render Markdown + React components (e.g., for interactive demos).
            - [ ] **Syntax Highlighting**: Integrate `rehype-prism` or `shiki` for code blocks.
        - **Backend / Data Tasks** (Node.js):
            - [ ] **File System Data Layer**: Write a service using Node's `fs` to recursively read `journal/` and parse Frontmatter (metadata).
            - [ ] **SSG Generation**: Implement `generateStaticParams` to build a static HTML page for every markdown file.
            - [ ] **Search Index**: Write a build-script to generate a `search.json` file containing all post content for client-side search.
        - **DevOps**:
            - [ ] **GitHub Actions**: Create a `.github/workflows/deploy.yml` to build and deploy to GitHub Pages on push.
[ ] React Patterns - Higher-Order Components, Custom Hooks, and Composition.
    - **Project: Form Builder Library**: Create a reusable `useForm` hook and a set of composed Input components that handle validation and errors generic.

### Backend

[ ] Ruby on Rails Advanced - Performance tuning, Background jobs (Sidekiq), and Metaprogramming.
    - **Project: Bulk Email Sender**: Allow users to upload a CSV of 10k users and send personalized emails using Sidekiq batches, handling retries and rate limits.
[ ] Redis in Rails - Caching strategies and transient state.
    - **Project: Rate Limiter Middleware**: Implement a custom Rack middleware (or use Kredis) to rate limit API requests by IP/User using Redis counters.
[ ] TypeScript Backend - Building type-safe services with Node.js.
    - **Project: Real-time Notification Service**: A microservice that accepts HTTP requests and broadcasts them to connected clients via WebSockets (Socket.io/ws), typed strictly with interfaces.
[ ] Redis with TypeScript - High-performance data structures.
    - **Project: Live Leaderboard**: Build a gaming leaderboard service using Redis Sorted Sets (ZSET) to handle millions of score updates and ranking queries in real-time.
[ ] RabbitMQ & Event-Driven Architecture - Messaging patterns for communication between Rails and TS services.
    - **Project: Image Processing Pipeline**:
        1. Rails app receives an image upload -> publishes `image.uploaded` event.
        2. TS Worker consumes event -> resizes/optimizes image -> publishes `image.processed`.
        3. Rails app consumes `image.processed` -> updates DB and notifies user.
[ ] Apache Kafka - Distributed event streaming and high-throughput data pipelines.
    - **Project: Real-time Analytics Dashboard**: Ingest clickstream events from the Frontend into a Kafka topic, process them with a consumer group to calculate rolling window stats (e.g., active users), and push updates to the dashboard via WebSockets.
[ ] API Design - Designing contracts shared between Rails/TS services and mobile clients.
    - **Project: Universal Schema**: Define a User Profile schema using OpenAPI/Swagger or Protobuf, and generate client SDKs (Swift/Kotlin/TS) automatically in a CI pipeline.

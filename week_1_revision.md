# Week 1 Revision Notes

**1. Key Performance Metrics**
- **Number of object requests**: Strongest predictor of page load time due to per-request overhead and latency.
- **Total bytes downloaded**: Important for bandwidth, but less predictive than request count.

**2. Origins & Third‑Party Resources**
- **First‑party vs. third‑party origin**: First‑party matches your site’s domain. Third‑party serves content from other domains (e.g. ad networks, CDNs).
- Risks of third‑party: increased DNS lookups, potential blocking, privacy/security concerns.

**3. Testing Methodologies**
- **Synthetic Tests**: Lab‑based, controlled environments simulating network and browser conditions.
- **Real User Monitoring (RUM)**: Collects performance data from actual users in production, reflecting true delivery conditions.

**4. HTTP/2 Features**
- **Multiplexing**: Allows multiple streams over a single TCP connection, reducing head‑of‑line blocking.
- **Server Push**: Proactively sends resources before the browser requests them (optional).

**5. Asset Optimization**
- **Minification**: Strips whitespace/comments from CSS/JS to reduce file sizes.
- **Bundling**: Combines multiple modules into one file to reduce request count.
- **Module Bundlers vs. Transpilers**: Webpack, Browserify, RequireJS are bundlers; Babel is a transpiler.

**6. Resource Hints**
- `<link rel="preload" href=...>`: Instructs browser to fetch critical resources early.
- `<link rel="dns-prefetch" href=...>`: Resolves DNS for domains in advance, cutting lookup time.

**7. Rendering Milestones**
- **TTFB (Time to First Byte)**: Time until first byte arrives from server.
- **FCP (First Contentful Paint)**: When first text/image is rendered.
- **CLS (Cumulative Layout Shift)**: Measures unexpected layout shifts during loading; lower is better.

**8. Caching Strategies**
- **Cache-Control: max-age**: Specifies how long a resource remains fresh in the browser cache.
- **ETags**: Unique identifiers for resources to validate cache.

**9. Core Technologies & Standards**
- **JSON (JavaScript Object Notation)**: Lightweight data‐interchange format.
- **REST (Representational State Transfer)**: Architectural style for networked applications.
- `<meta charset="UTF-8">`: Declares document’s character encoding.

**10. Load Optimization**
- **Script Placement**: Placing `<script>` tags at the end of `<body>` prevents blocking HTML parsing.
- **Async vs. Defer**: `async` executes immediately on load; `defer` waits until parsing completes.

---
*Review these concepts to solidify your understanding before moving on to Week 2.*


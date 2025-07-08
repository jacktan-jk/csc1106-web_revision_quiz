# Week 9 Revision Notes

**1. OWASP and Security Standards**
- **OWASP (Open Web Application Security Project)**: Community-driven organization; publishes the **OWASP Top Ten**, a list of the most critical web application security risks.
- **Content Security Policy (CSP)**: HTTP header that restricts sources of scripts, styles, and other resources to mitigate Cross-Site Scripting (XSS).

**2. Framework & Server Fingerprinting**
- **HTTP Headers**:
  - `Server`: reveals web server software and version.
  - `X-Powered-By`: often discloses underlying framework (e.g., `Express`, `PHP/7.4`).
- **URL Paths & Cookies**:
  - Paths like `/wp-content/` indicate WordPress.
  - Cookie names (e.g. `APP_KEY`) can hint Laravel.
  - File extensions (`.aspx`) reveal ASP.NET; (`.php`) reveals PHP.

**3. Deployment & Cloud Storage Testing**
- **Cloud Storage Access**:
  - **Read**: `curl -X GET https://bucket.example.com/path`
  - **Write**: `curl -X PUT --data-binary @file ...`
- **Permission Checks**: Validate bucket policies and ACLs via HTTP methods.

**4. Performance Optimization**
- **Lazy Loading**: Defer loading images and non-critical assets until they appear in the viewport.
- **Code Splitting**: Break JavaScript bundles into smaller chunks to load only necessary code on initial page load.
- **Async/Defer Scripts**:
  - `async`: downloads script and executes immediately when ready (may interrupt parsing).
  - `defer`: downloads script and executes after HTML parsing completes.
- **Compression**: Enable **Gzip** and **Brotli** on server to shrink payload sizes.
- **Content Delivery Network (CDN)**: Distribute assets geographically to reduce latency.

**5. Caching & HTTP/2 Enhancements**
- **Resource Hints**: `preload`, `prefetch`, `preconnect`, and `dns-prefetch` to optimize critical resources.
- **HTTP/2 Multiplexing**: Reduces request overhead by sending multiple streams over one connection.

**6. Architecture Patterns**
- **Monolith**:
  - Single deployable unit, simple to develop but single point of failure and hard to scale selectively.
- **Microservices**:
  - Independent services that can scale separately; adds network complexity but improves resilience and deployability.

**7. Database Optimization**
- **Partitioning**: Splits large tables into smaller, manageable pieces based on ranges or keys.
- **Connection Pooling**: Reuses database connections (e.g., via `r2d2` or `sqlx`) to reduce overhead.
- **MVCC (Multi-Version Concurrency Control)**: PostgreSQL feature allowing high concurrency without locking conflicts.

**8. Caching Layers**
- **In-Memory Caching**: Redis or Memcached for storing frequent queries or session data.
- **Browser Caching**: Leverage `Cache-Control` and `ETag` for client-side caching.

**9. Security Posture**
- Regularly update dependencies and scan for known vulnerabilities (e.g., `npm audit`, OS package scanning).
- Harden HTTP headers: `X-Content-Type-Options: nosniff`, `X-Frame-Options: DENY`, `Referrer-Policy`, and CSP.
- Implement centralized logging and monitoring for anomalous patterns (e.g., excessive errors or unusual endpoints hit).

---
*These notes summarize deployment strategies, performance tuning, and security best practices covered in Week 9.*


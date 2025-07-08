# Week 4 Revision Notes

**1. Middleware in Web Frameworks**
- **Definition**: Reusable components that intercept and modify HTTP requests/responses before they reach final route handlers.
- **Actix-Web Traits**: Implement the `Transform` and `Service` traits to compose middleware into the service pipeline.

**2. Common Middleware Types**
- **Logger**: Records request method, path, status code, and response time.
- **Compress**: Applies gzip or Brotli compression to outgoing responses.
- **NormalizePath**: Consistently handles trailing slashes in URLs.
- **CORS (Cross-Origin Resource Sharing)**: Adds `Access-Control-Allow-*` headers to permit cross-domain requests.
- **ErrorHandlers**: Captures errors and renders custom error pages or JSON responses.

**3. Security Policies**
- **Same-Origin Policy**: Browser policy restricting scripts from accessing resources on different domains.
- **CORS Preflight**: Browsers send an `OPTIONS` request to validate cross-origin permissions before the actual request.
  - Key header: `Access-Control-Allow-Origin`

**4. Client Modules & Asynchronous Event Handling**
- **Asynchronous (async)**: Handles I/O (network requests, file uploads) and event-driven code (user input) without blocking.
- **Synchronous (sync)**: Pure functions and state updates that run immediately, returning values.
- **Separation Benefits**:
  - Easier unit testing of pure sync logic.
  - Clearer error localization.
- **Drawbacks**: Increased boilerplate and module complexity.

**5. File & Resource Naming Strategies**
- **Hash-based**: Use a content hash in the filename to ensure cache busting when content changes.
- **Timestamp-based**: Include epoch timestamps for simple versioning.
- **Database-record ID**: Name files using a unique database ID and store metadata separately.

**6. HTTP Methods & Idempotency**
- **PUT**: Idempotent—multiple identical requests yield same server state.
- **PATCH**: Non-idempotent partial updates—applies only specified changes.
- **OPTIONS**: Used for CORS preflight checks, not for data retrieval or mutation.

**7. Testing Strategies**
- **Sync Logic**: Unit test pure functions without side effects.
- **Async Modules**:
  - Use mock servers or HTTP intercepts to simulate backend responses.
  - Avoid real network calls to ensure test isolation.

---
*Review middleware patterns, client-side architecture, and HTTP fundamentals before moving on to Week 5.*


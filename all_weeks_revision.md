# Comprehensive Revision Notes (Weeks 1, 2, 4, 5, 8 & 9)

---
## Week 1: Web Performance Fundamentals

### Key Concepts
- **Object Requests** vs **Total Bytes**: Minimize HTTP requests (object count) for best load-time gains.
- **Synthetic Tests** vs **RUM (Real User Monitoring)**
- **HTTP/2**: Multiplexing, Server Push
- **Asset Optimization**: Minification, Bundling
- **Resource Hints**: `preload`, `dns-prefetch`
- **Rendering Milestones**: TTFB, FCP, CLS
- **Caching**: `Cache-Control`, `ETag`

### Acronyms & Abbreviations
| Acronym | Expansion                          |
|---------|------------------------------------|
| TTFB    | Time To First Byte                 |
| FCP     | First Contentful Paint             |
| CLS     | Cumulative Layout Shift            |
| RUM     | Real User Monitoring               |
| WPO     | Web Performance Optimization       |

### Diagrams
**Critical Rendering Path**
```
HTML
 ↓ parse
DOM
 ↓ combine with CSS
Render Tree
 ↓ layout
Layout Tree
 ↓ paint
Painted Pixels
```

**HTTP/2 Multiplexing**
```
Client                                  Server
 Stream1 ─┐                            ┌─►Handler
 Stream2 ─┼─► Single TCP Connection ───┼
 Stream3 ─┘                            └─►Handler
```  

**Resource Hint Timeline**
```
HTML parse → <link rel="preload"> → Browser fetch → Rendering begins
```

---
## Week 2: Rust Programming Essentials

### Key Concepts
- Functions (`fn`) vs Macros (`!`)
- **Ownership** & **Borrowing** rules
- **Move** vs **Clone**
- The unit type `()` and generics
- **RAII** and memory safety without GC
- **WASM** (WebAssembly) via `wasm-bindgen`
- JSON (de)serialization with **Serde**

### Acronyms & Abbreviations
| Acronym | Expansion                         |
|---------|-----------------------------------|
| RAII    | Resource Acquisition Is Initialization |
| WASM    | WebAssembly                       |
| JSON    | JavaScript Object Notation        |

### Diagrams
**Ownership & Borrowing**
```
let a = Data;
let b = a;     // Move: a invalidated
let c = b.clone(); // Clone: b still valid
let r = &c;    // Immutable borrow
let m = &mut c; // Mutable borrow (exclusive)
```

**Macro Expansion Flow**
```
Source code with macros
 ↓ compile-time
Macro expands into Rust code
 ↓ compilation
Standard Rust code is compiled and optimized
```

---
## Week 4: Middleware & HTTP Fundamentals

### Key Concepts
- **Middleware**: `Transform` & `Service` traits in Actix-Web
- Common middleware: Logger, Compress, NormalizePath, CORS, ErrorHandlers
- **Same-Origin Policy** and **CORS preflight** (`OPTIONS` + `Access-Control-Allow-Origin`)
- Async vs Sync client modules; testing with mock servers
- File naming: hash, timestamp, DB ID strategies
- HTTP methods: `PUT` (idempotent), `PATCH` (partial), `OPTIONS` (preflight)

### Acronyms & Abbreviations
| Acronym | Expansion                          |
|---------|------------------------------------|
| CORS    | Cross-Origin Resource Sharing      |
| API     | Application Programming Interface  |
| HTTP    | HyperText Transfer Protocol        |

### Diagrams
**Middleware Pipeline**
```
Client → [Middleware1] → [Middleware2] → Handler → Response
```

**CORS Preflight**
```
Browser → OPTIONS /api/data → Server (Access-Control-Allow-Origin)
```

---
## Week 5: Databases & Templates

### Key Concepts
- **SQLite** vs **PostgreSQL (MVCC)** vs **MySQL (InnoDB)**
- ACID properties: Atomicity, Consistency, Isolation, Durability
- Indexing (`CREATE INDEX`), Partitioning, Connection Pooling, Caching (Redis)
- `.env` files via **dotenv**
- **ORM**: Diesel (sync), SeaORM (async)
- Templating (Tera): `{{ var }}`, `{% for %}`, inheritance, partials
- SSR vs CSR tradeoffs

### Acronyms & Abbreviations
| Acronym | Expansion                          |
|---------|------------------------------------|
| ACID    | Atomicity, Consistency, Isolation, Durability |
| ORM     | Object-Relational Mapping         |
| CSR     | Client-Side Rendering             |
| SSR     | Server-Side Rendering             |

### Diagrams
**ACID Transaction Flow**
```
BEGIN;
UPDATE balances;
INSERT logs;
COMMIT;  // all or nothing
```

**Template Inheritance**
```
base.html: {% block content %}{% endblock %}
child.html: {% extends "base.html" %} {% block content %}Hello{% endblock %}
```

---
## Week 8: Authentication & Security

### Key Concepts
- **Authentication** vs **Authorization**
- Authentication factors: knowledge, possession, inherence; 2FA
- Password salting & hashing (bcrypt, Argon2), **HMAC**
- Cookies: `Set-Cookie`, HttpOnly, Secure, SameSite
- Session fixation/hijacking mitigations (rotate IDs, short TTL)
- CSRF defenses: tokens + SameSite
- XSS defenses: CSP, output encoding, HttpOnly

### Acronyms & Abbreviations
| Acronym | Expansion                           |
|---------|-------------------------------------|
| 2FA     | Two-Factor Authentication           |
| HMAC    | Hash-based Message Authentication Code |
| CSRF    | Cross-Site Request Forgery          |
| XSS     | Cross-Site Scripting                |
| CSP     | Content Security Policy             |

### Diagrams
**Session Fixation Mitigation**
```
User logs in
→ Generate NEW session ID
→ Store on client
```

**CSRF Token Flow**
```
Form → <input name="csrf_token" value="XYZ">
Server validates XYZ on POST
```

---
## Week 9: Deployment & Performance

### Key Concepts
- **OWASP Top Ten** and **CSP** headers
- Server fingerprinting: `Server`, `X-Powered-By`, URLs, cookie names
- Cloud storage tests: `curl GET`, `curl PUT`
- Lazy loading, code splitting, async/defer, Gzip/Brotli, CDNs
- Resource hints: `preload`, `prefetch`, `preconnect`, `dns-prefetch`
- Monolith vs Microservices tradeoffs
- Partitioning, connection pooling, MVCC (PostgreSQL)
- Caching layers: Redis, browser cache headers
- Security posture: header hardening, dependency scans, logging

### Acronyms & Abbreviations
| Acronym | Expansion                          |
|---------|------------------------------------|
| OWASP   | Open Web Application Security Project |
| CDN     | Content Delivery Network           |
| MVCC    | Multi-Version Concurrency Control  |
| DDoS    | Distributed Denial of Service      |
| ACL     | Access Control List                |

### Diagrams
**Lazy Loading Flow**
```
Page load → placeholder → element enters viewport → actual resource fetch
```

**Microservices vs Monolith**
```
Monolith: [AppAll]
Microservices: [Auth]—[API]—[UI]—[Payments]
```

---
*Use this consolidated guide for high-level review across all weeks.*


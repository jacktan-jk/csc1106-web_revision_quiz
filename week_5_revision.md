# Week 5 Revision Notes

**1. Database Types & Characteristics**
- **SQLite**: Embedded, serverless, single-file, zero‐configuration, public domain.
- **PostgreSQL**: Client‐server, MVCC (Multi-Version Concurrency Control) for high concurrency, supports JSONB, custom types (arrays, enums), PostGIS extension.
- **MySQL (InnoDB)**: Common in LAMP stacks, client‐server, row‐level locking.

**2. ACID Properties**
- **Atomicity**: All-or-nothing transactions.
- **Consistency**: Database remains valid before and after transactions.
- **Isolation**: Concurrent transactions do not interfere.
- **Durability**: Committed changes survive failures.

**3. Indexing & Performance**
- **CREATE INDEX**: Speeds lookups on large tables.
- **Partitioning**: Splits tables into segments for manageability.
- **Connection Pooling**: Reuses database connections (e.g. via `r2d2` in Rust) for low-latency, high-throughput.
- **Caching**: Use in-memory stores (Redis, Memcached) to reduce database load.

**4. Environment Configuration**
- **.env file**: Stores environment variables (e.g. database URLs, API keys) outside code.
- **dotenv crate**: Loads `.env` into `std::env` at application start.

**5. Object-Relational Mapping (ORM)**
- **ORM**: Bridges between Rust structs and relational tables.
- **Diesel**: Compile-time schema validation, type-safe queries.
- **SeaORM**: Async ORM for Rust, supports dynamic queries.

**6. Template Engines**
- **Purpose**: Combine static templates with dynamic data to render text/HTML on the server.
- **Tera**: Jinja2-inspired Rust library; uses `{{ variable }}` for interpolation and `{% for ... %}` / `{% if ... %}` for logic.
- **Template inheritance**: Define base layouts and override blocks in child templates to DRY common structure.
- **Partials**: Reusable sub-templates (headers, footers) included via `{% include "partial.html" %}`.

**7. Rendering Strategies**
- **SSR (Server-Side Rendering)**: Server generates full HTML before sending to client. Good for SEO and initial load speed.
- **CSR (Client-Side Rendering)**: Server sends minimal shell HTML and JavaScript; browser builds UI dynamically. Good for interactivity.

**8. Security & Best Practices**
- **Parameterize queries** to prevent SQL injection.
- **Never commit `.env`** to version control; add to `.gitignore`.
- **Strict typing** and compile‐time checks in ORM reduce runtime errors.

---
*Review these database and templating concepts before moving on to Week 8.*


# Week 8 Revision Notes

**1. Authentication vs. Authorization**
- **Authentication**: Verifies the identity of a user ("who are you?").
- **Authorization**: Determines what actions or resources an authenticated user may access ("what can you do?").

**2. Authentication Factors**
- **Something you know**: Passwords, PINs.
- **Something you have**: Hardware token, mobile authenticator.
- **Something you are**: Biometric (fingerprint, face ID).
  - **Two-Factor Authentication (2FA)**: Combines any two of the above for enhanced security.

**3. Password Security**
- **Salting**: Add a unique random value to each password before hashing to prevent rainbow‑table attacks.
- **Hashing**: Use strong one‑way functions (bcrypt, Argon2) — never store plaintext.
- **HMAC (Hash-based Message Authentication Code)**: Ensures data integrity and authenticity when verifying messages.

**4. Cookies & Session Management**
- **Set-Cookie header**: Instructs browser to store a cookie.
- **Cookie header**: Sent by browser on subsequent requests.
- **HttpOnly flag**: Prevents JavaScript access to cookies, mitigating XSS theft.
- **Secure flag**: Ensures cookies are sent only over HTTPS.
- **SameSite attribute**: Controls cross‑site sending of cookies to mitigate CSRF:
  - `Strict`, `Lax`, or `None` values determine when cookies are included.

**5. Session Vulnerabilities & Mitigations**
- **Session fixation**: Attacker sets or predicts a user’s session ID. _Mitigation_: Rotate session ID upon login.
- **Session hijacking**: Theft of valid session cookies (e.g. via XSS). _Mitigation_: HttpOnly, Secure, short expiration.

**6. Cross-Site Request Forgery (CSRF)**
- **CSRF attacks**: Malicious requests forged from authenticated user’s browser.
- **Mitigations**:
  - **CSRF tokens**: Unique, per‑session, per‑request tokens embedded in forms and validated server‑side.
  - **SameSite cookies**: Restrict sending cookies on cross‑site requests.

**7. Cross-Site Scripting (XSS)**
- **XSS**: Injection of malicious scripts into trusted websites.
- **Impact**: Can steal cookies, deface content, perform actions on behalf of users.
- **Mitigations**: Output encoding, Content Security Policy (CSP), HttpOnly cookies.

**8. HTTP Authentication**
- **Basic Auth**: Encodes credentials in Base64 in the `Authorization` header; impractical without HTTPS/session reuse.
- **Digest Auth**: Uses nonce values to prevent replay, but largely superseded by token‑based schemes.

**9. Best Practices**
- Always enforce HTTPS and use the `Secure` cookie flag.
- Employ short session lifetimes and rotate IDs on elevation of privilege.
- Use strong, salted, hashed passwords (bcrypt/Argon2).
- Implement CSP headers to reduce XSS risk.
- Centralize authentication logic and audit logs for suspicious activity.

---
*Review these security fundamentals before moving on to Week 9.*


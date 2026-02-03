# Sentinel Journal

## 2025-05-15 - Strict Input Sanitization
**Vulnerability:** Use of `stripslashes` instead of `wp_unslash`.
**Learning:** `wp_unslash` is context-aware and handles array recursion correctly, whereas `stripslashes` does not. WP standards mandate `wp_unslash` for input handling.
**Prevention:** Always use `wp_unslash` when processing `$_POST`/`$_GET` data.

## 2025-05-20 - DOM XSS via Attribute Context
**Vulnerability:** `escapeHtml` implementation using `div.textContent` does not escape double quotes, making it unsafe for attribute injection (e.g., `title="..."`).
**Learning:** Browsers do not escape quotes when retrieving `innerHTML` from `textContent` assignment. This is a subtle but critical difference from PHP's `htmlspecialchars`.
**Prevention:** Use regex-based replacement for `&`, `<`, `>`, `"`, and `'` when escaping for HTML context, especially if used in attributes.

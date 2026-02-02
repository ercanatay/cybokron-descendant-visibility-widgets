# Sentinel Journal

## 2025-05-15 - Strict Input Sanitization
**Vulnerability:** Use of `stripslashes` instead of `wp_unslash`.
**Learning:** `wp_unslash` is context-aware and handles array recursion correctly, whereas `stripslashes` does not. WP standards mandate `wp_unslash` for input handling.
**Prevention:** Always use `wp_unslash` when processing `$_POST`/`$_GET` data.

## 2025-05-15 - Strict ID Validation
**Vulnerability:** Loose validation allowing non-numeric values for ID-based fields (pages, categories).
**Learning:** `sanitize_text_field` is insufficient for ID fields; it cleans HTML but allows strings where integers are expected.
**Prevention:** Use `absint()` or `intval()` for all fields expected to be database IDs.

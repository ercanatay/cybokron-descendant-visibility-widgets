## 2025-02-12 - Prefer wp_unslash over stripslashes
**Vulnerability:** The project used `stripslashes` for input sanitization, which is discouraged in WordPress context.
**Learning:** `wp_unslash` is the standard WordPress function for removing slashes, and it handles both strings and arrays recursively, ensuring consistent behavior across the platform.
**Prevention:** Use `wp_unslash` instead of `stripslashes` when handling slashed data (like `$_POST` or `$_GET` in WordPress).

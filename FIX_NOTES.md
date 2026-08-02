# Rendering fix

The redesigned pages are stored as `.html` files under `_pages/` so Jekyll processes Liquid and layouts without running the page body through Kramdown. This prevents nested HTML indentation from being converted into code blocks.

The stylesheet is now served directly as `css/main.css`; no Sass build is required for the redesigned theme.

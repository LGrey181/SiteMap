# SiteMap

SiteMap crawls links within a domain and writes the discovered pages as an XML sitemap to standard output.

## Requirements

- Go 1.27 or newer
- Network access to the site being crawled

## Usage

Run the application with the Go toolchain. The default starting URL is the Gophercises website, and the default maximum traversal depth is 3.

The starting page is set with the `url` flag. The maximum number of link levels to visit is set with the `depth` flag. The generated XML can be redirected to a sitemap file or passed to another command for further processing.

## Behavior

- Only links that stay on the starting domain are included.
- Relative links are resolved against the page's domain.
- Pages are visited at most once.
- The crawler follows HTTP links found in page content.
- Network and page parsing errors are skipped, so incomplete results are possible.

## Output

The output follows the Sitemap XML 0.9 format and contains one location entry for each discovered page.

## Development

Dependencies are managed with Go modules. Run the project's tests and standard Go checks before submitting changes.

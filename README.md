## Deployment Notes (Cloudflare Wrangler)

If you are deploying this project to Cloudflare using Wrangler, you may encounter the following warnings in your console logs during deployment:

> ▲ [WARNING] Because 'workers_dev' is not in your Wrangler file, it will be enabled for this deployment by default.
> ▲ [WARNING] Because your 'workers.dev' route is enabled and your 'preview_urls' setting is not in your Wrangler file, Preview URLs will be enabled for this deployment by default.

### How to resolve these warnings:

These warnings appear because Wrangler is defaulting to enabling `workers.dev` and `preview_urls` since they aren't explicitly defined. To clear the warnings, create or update a `wrangler.toml` file in the root directory of this repository and explicitly declare your preferences.

Add the following to your `wrangler.toml`:

```toml
name = "code-translator"
compatibility_date = "2024-05-05" 

# To explicitly accept the defaults and remove the warnings:
workers_dev = true
preview_urls = true

# Alternatively, if you are strictly using a custom domain and want them off:
# workers_dev = false
# preview_urls = false

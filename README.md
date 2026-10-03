# CINMAA Carousel Engine

A single-file web app. `index.html` holds everything it needs.

## Deploy on GitHub Pages

1. Create a new repository on GitHub, for example `cinmaa-carousel`.
2. Click **Add file › Upload files**, drag in `index.html` and this README, then click **Commit changes**.
3. Go to **Settings › Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then click **Save**.
4. After a minute or two your app is live at `https://<your-username>.github.io/cinmaa-carousel/`.

## Using a custom domain (e.g. app.cinmaa.com)

In **Settings › Pages › Custom domain**, enter the domain. At your domain provider, add a CNAME record pointing `app` to `<your-username>.github.io`.

## Publish to cinmaa.com (WordPress)

One-time setup:

1. Log in to `cinmaa.com/wp-admin` as an Administrator or Editor.
2. Go to **Users › Profile**, scroll to **Application Passwords**, type `CINMAA Engine`, click **Add New Application Password**, and copy the password. It's shown only once.
3. In the app, open **Settings › Your website**. Enter `https://cinmaa.com`, your WordPress username and the application password. Set categories (default `Blog, Stories`) and what to include.
4. Click **Test connection**.

After that, every carousel has a **Publish to website** button. Each post includes:

- the motion video at the top
- the article
- a gallery of the slides, with the first slide as the featured image
- a PDF download link
- the caption and hashtags

It uses the SEO title, slug and meta description as the post title, slug and excerpt. Hashtags become WordPress tags. Save to archive after publishing; publishing that carousel again then updates the same post instead of creating a duplicate.

The video records in real time, so keep the tab in front while it records.

### If Test connection fails

- **No Application Passwords section:** the site must use HTTPS, and a security plugin (Wordfence, iThemes, etc.) may have turned the feature off. Turn it back on in that plugin's settings.
- **"Refused the login" even though the password is correct:** some hosts strip the login header. Add this near the top of `.htaccess` in the WordPress folder:
  ```
  RewriteEngine On
  RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
  ```
- **"Couldn't reach the site":** a security plugin or firewall (e.g. Cloudflare) is blocking the REST API (`/wp-json/`). Allow it for logged-in users. Use the GitHub Pages copy of the app rather than a file opened from your computer.
- **Large videos fail:** raise `upload_max_filesize` and `post_max_size` (e.g. 256M) in your hosting control panel.

## Notes

- Choose a writing engine in the app's Settings tab: an Anthropic key, an OpenAI-compatible key, or Manual (paste the prompt into any AI).
- API keys, the WordPress password and the archive are stored in each visitor's own browser. Don't put a key in a public copy someone else will use.

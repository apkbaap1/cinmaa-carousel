# CINMAA Carousel Engine

A single-file web app. `index.html` holds everything it needs.

## Deploy on GitHub Pages

1. Create a new repository on GitHub, for example `cinmaa-carousel`.
2. Click **Add file › Upload files**, drag in `index.html` and this README, then click **Commit changes**.
3. Go to **Settings › Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then click **Save**.
4. After a minute or two your app is live at `https://<your-username>.github.io/cinmaa-carousel/`.

## Using a custom domain (e.g. app.cinmaa.com)

In **Settings › Pages › Custom domain**, enter the domain. At your domain provider, add a CNAME record pointing `app` to `<your-username>.github.io`.

## Notes

- Choose a writing engine in the app's Settings tab: an Anthropic key, an OpenAI-compatible key, or Manual (paste the prompt into any AI).
- API keys and the archive are stored in each visitor's own browser. Don't put a key in a public copy someone else will use.

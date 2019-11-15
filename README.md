# Shifter Deploy to Netlify as a Subdirectory

Netlify build script and redirects for deploying a static WordPress site from Shifter to Netlify in a subdirectory.

<a href="https://app.netlify.com/start/deploy?repository=https://github.com/getshifter/netlify-build-subdir"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify"></a>

# How to

## On Netlify
1. Deploy this to Netlify
1. Navigate to deploy settings, add a build hook
1. Name the build hook, we called ours "Shifter Artifact Webhook", save it
1. Copy the new build hook URL, e.g. "https://api.netlify.com/build_hooks/abc123"

## On Shifter
1. Migrate or launch a new WordPress site on Shifter
1. Select a plan that support webhooks
1. Navigate to webhook settings, paste your Netlify build hook URL, save it
1. Generate a new artifact

## Explained
This process does 2 things. First, it sets up a Netlify site with the required build settings and redirects. Those settings are located within the `netlify.toml` file and `build.sh`.

The `build.sh` includes a few necessary search and replace scripts to enable support for a subdirectory site install such as `example.com/blog`.

The `netlify.toml` file includes the redirects and subdirectory path. In this example, we're using `/blog/`.
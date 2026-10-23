# Chef portfolio

Static site with a Decap CMS editor at /admin. No build step.

## Files
- index.html: the site (reads content/site.json)
- content/site.json: all text, dishes, and career steps
- admin/: the editor (config.yml controls the forms)
- images/uploads/: photos uploaded through the editor

## Preview on your computer
Browsers block the content file when opening index.html directly. Run a local server instead:

    npx decap-server        # terminal 1 (lets /admin save locally)
    python3 -m http.server  # terminal 2, then open http://localhost:8000

Open http://localhost:8000/admin to try the editor. Remove `local_backend: true` from admin/config.yml before going live.

## Go live
1. Create a GitHub repository and push these files to the main branch.
2. In admin/config.yml, replace YOUR-GITHUB-USERNAME/chef-portfolio with your repository.
3. On Netlify: Add new site > Import from Git > pick the repository. Leave the build command empty.
4. In Netlify: Project configuration > Access & security > OAuth > Install provider > GitHub. Enter the client ID and secret from a GitHub OAuth app (GitHub > Settings > Developer settings > OAuth Apps). Use https://api.netlify.com/auth/done as the callback URL.
5. Visit yoursite.com/admin, log in with GitHub, and edit. Each save publishes in about a minute.
6. Add your custom domain in Netlify > Domain management.

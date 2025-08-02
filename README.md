# Personal-Site

This is a personal website built with [Hugo](https://gohugo.io/), a fast static site generator, using the [Congo](https://jpanther.github.io/congo/) theme.

## Install Hugo

### Prequesites
Instructions and links for both steps can be found at the [hugo installation](https://gohugo.io/installation/) page. 

1. Install `go`

2. Install `dart saas`

### Install Hugo

1. **macOS (Homebrew):**
   ```sh
   brew install hugo
   ```
2. **Other platforms:** See [Hugo install docs](https://gohugo.io/getting-started/installing/) for platform-specific instructions.

## Running the Site Locally

1. Clone the repository:
   ```sh
   git clone https://github.com/garrett928/Personal-Site.git
   cd Personal-Site
   ```
2. Start the Hugo development server:
   ```sh
   hugo server
   ```
3. Visit [http://localhost:1313](http://localhost:1313) in your browser to view the site.

## Making Changes

- **Content:** Edit or add Markdown files in the `content/` directory (e.g., `about/`, `projects/`, `Resume/`).
- **Configuration:** Update site settings in `config/_default/config.toml`.
- **Theme Customization:** Adjust theme options in the config file or override layouts/shortcodes in `layouts/`.
- **Static Assets:** Add images and files to `static/` or `assets/`.

## Rebuilding the Site

For production builds (generates static files in `public/`):

```sh
hugo
```

## Deploying / Pushing to GitHub

1. Stage and commit your changes:
   ```sh
   git add .
   git commit -m "Update site content or configuration"
   ```
2. Push to GitHub:
   ```sh
   git push origin main
   ```


## Additional Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Congo Theme Documentation](https://jpanther.github.io/congo/docs/)

---

## Theme Management Note

This site uses the Hugo Modules method to manage the Congo theme. Theme dependencies are handled via the `go.mod` and `go.sum` files, allowing Hugo to automatically fetch and update the theme as needed. No manual downloads or git submodules are required. For more details, see the [Hugo Modules documentation](https://gohugo.io/hugo-modules/usage/).
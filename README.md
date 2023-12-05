<br>
<img src="https://raw.githubusercontent.com/ultralytics/assets/main/logo/Ultralytics_Logotype_Original.svg" width="320">

# Ultralytics Docs

Ultralytics Docs are deployed to [https://docs.ultralytics.com](https://docs.ultralytics.com).

[![pages-build-deployment](https://github.com/ultralytics/docs/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/ultralytics/docs/actions/workflows/pages/pages-build-deployment)  [![Check Broken links](https://github.com/ultralytics/docs/actions/workflows/links.yml/badge.svg)](https://github.com/ultralytics/docs/actions/workflows/links.yml)

### Install Ultralytics package

[![PyPI version](https://badge.fury.io/py/ultralytics.svg)](https://badge.fury.io/py/ultralytics) [![Downloads](https://static.pepy.tech/badge/ultralytics)](https://pepy.tech/project/ultralytics)

To install the ultralytics package in developer mode, you will need to have Git and Python 3 installed on your system. Then, follow these steps:

1. Clone the ultralytics repository to your local machine using Git:

    ```bash
    git clone https://github.com/ultralytics/ultralytics.git
    ```

2. Navigate to the root directory of the repository:

    ```bash
    cd ultralytics
    ```

3. Install the package in developer mode using pip:

    ```bash
    pip install -e '.[dev]'
    ```

This will install the ultralytics package and its dependencies in developer mode, allowing you to make changes to the package code and have them reflected immediately in your Python environment.

Note that you may need to use the pip3 command instead of pip if you have multiple versions of Python installed on your system.

### Building and Serving Locally

The `mkdocs serve` command is used to build and serve a local version of the MkDocs documentation site. It is typically used during the development and testing phase of a documentation project.

```bash
mkdocs serve
```

Here is a breakdown of what this command does:

- `mkdocs`: This is the command-line interface (CLI) for the MkDocs static site generator. It is used to build and serve MkDocs sites.
- `serve`: This is a subcommand of the `mkdocs` CLI that tells it to build and serve the documentation site locally.
- `-a`: This flag specifies the hostname and port number to bind the server to. The default value is `localhost:8000`.
- `-t`: This flag specifies the theme to use for the documentation site. The default value is `mkdocs`.
- `-s`: This flag tells the `serve` command to serve the site in silent mode, which means it will not display any log messages or progress updates. When you run the `mkdocs serve` command, it will build the documentation site using the files in the `docs/` directory and serve it at the specified hostname and port number. You can then view the site by going to the URL in your web browser.

While the site is being served, you can make changes to the documentation files and see them reflected in the live site immediately. This is useful for testing and debugging your documentation before deploying it to a live server.

To stop the serve command and terminate the local server, you can use the `CTRL+C` keyboard shortcut.

### Building and Serving Multi-Language

For multi-language MkDocs sites use the following additional steps:

1. Add all new language *.md files to git commit: `git add docs/**/*.md -f`
2. Build all languages to the `/site` directory. Verify that the top-level `/site` directory contains `CNAME`, `robots.txt` and `sitemap.xml` files, if applicable.

    ```bash
    # Remove existing /site directory
    rm -rf site

    # Loop through all *.yml files in the docs directory
    mkdocs build -f docs/mkdocs.yml
    for file in docs/mkdocs_*.yml; do
      echo "Building MkDocs site with configuration file: $file"
      mkdocs build -f "$file"
    done
    ```

3. Preview in web browser with:

    ```bash
    cd site
    python -m http.server
    open http://localhost:8000  # on macOS
    ```

### Deploying Your Documentation Site

To deploy your MkDocs documentation site, you will need to choose a hosting provider and a deployment method. Some popular options include GitHub Pages, GitLab Pages, and Amazon S3.

Before you can deploy your site, you will need to configure your `mkdocs.yml` file to specify the remote host and any other necessary deployment settings.

Once you have configured your `mkdocs.yml` file, you can use the `mkdocs deploy` command to build and deploy your site. This command will build the documentation site using the files in the `docs/` directory and the specified configuration file and theme, and then deploy the site to the specified remote host.

For example, to deploy your site to GitHub Pages using the gh-deploy plugin, you can use the following command:

```bash
mkdocs gh-deploy
```

If you are using GitHub Pages, you can set a custom domain for your documentation site by going to the "Settings" page for your repository and updating the "Custom domain" field in the "GitHub Pages" section.

![196814117-fc16e711-d2be-4722-9536-b7c6d78fd167](https://user-images.githubusercontent.com/26833433/210150206-9e86dcd7-10af-43e4-9eb2-9518b3799eac.png)

For more information on deploying your MkDocs documentation site, see the [MkDocs documentation](https://www.mkdocs.org/user-guide/deploying-your-docs/).

# Contribute

We love your input! Ultralytics open-source efforts would not be possible without help from our community. Please see our [Contributing Guide](https://docs.ultralytics.com/help/contributing) to get started, and fill out our [Survey](https://ultralytics.com/survey?utm_source=github&utm_medium=social&utm_campaign=Survey) to send us feedback on your experience. Thank you 🙏 to all our contributors!

<!-- SVG image from https://opencollective.com/ultralytics/contributors.svg?width=990 -->
<a href="https://github.com/ultralytics/yolov5/graphs/contributors">
<img width="100%" src="https://github.com/ultralytics/assets/raw/main/im/image-contributors.png" alt="Ultralytics open-source contributors"></a>

# License

Ultralytics offers two licensing options to accommodate diverse use cases:

- **AGPL-3.0 License**: This [OSI-approved](https://opensource.org/licenses/) open-source license is ideal for students and enthusiasts, promoting open collaboration and knowledge sharing. See the [LICENSE](https://github.com/ultralytics/ultralytics/blob/main/LICENSE) file for more details.
- **Enterprise License**: Designed for commercial use, this license permits seamless integration of Ultralytics software and AI models into commercial goods and services, bypassing the open-source requirements of AGPL-3.0. If your scenario involves embedding our solutions into a commercial offering, reach out through [Ultralytics Licensing](https://ultralytics.com/license).

# Contact

For Ultralytics bug reports and feature requests please visit [GitHub Issues](https://github.com/ultralytics/xview-yolov3/issues), and join our [Discord](https://ultralytics.com/discord) community for questions and discussions!

<br>
<div align="center">
  <a href="https://github.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-github.png" width="3%" alt="Ultralytics GitHub"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.linkedin.com/company/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-linkedin.png" width="3%" alt="Ultralytics LinkedIn"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://twitter.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-twitter.png" width="3%" alt="Ultralytics Twitter"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://youtube.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-youtube.png" width="3%" alt="Ultralytics YouTube"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.tiktok.com/@ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-tiktok.png" width="3%" alt="Ultralytics TikTok"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.instagram.com/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-instagram.png" width="3%" alt="Ultralytics Instagram"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://ultralytics.com/discord"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-discord.png" width="3%" alt="Ultralytics Discord"></a>
</div>

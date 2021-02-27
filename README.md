# Yhi's Personal World Wide Web Site

This repository contains the source files of [www.yhi.moe](https://www.yhi.moe/).

- Static Web site generator: [Jekyll](https://jekyllrb.com/)
- Jekyll theme used: [Minima (RDFa linked version)](https://github.com/lmy441900/minima)

## Build

```sh
# Install Bundler (https://bundler.io/)
gem install bundler

# Bundler installs dependencies according to Gemfile(.lock)
bundler install jekyll

# Generate the site to ./_site/
# Serve it directly with `bundler exec jekyll serve`
bundler exec jekyll build
```

## Implicit Files

Since the Jekyll theme Minima is installed as a Ruby Gem, all files provided by Minima will first be used, and then the files in this repository. In other words, all files here are overriding what the theme is providing. This helps keeping the repository lean.

## License

Different contents are licensed under different terms:

- Site-related source files (including the Gemfile, HTML files, and CSS / Sass files) are licensed under [the MIT license](https://choosealicense.com/licenses/mit/); see [LICENSE-MIT](LICENSE-MIT).
- Original articles and web page contents are licensed under [the CC-BY-SA 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/); see [LICENSE-CC](LICENSE-CC).
- Personal information is public on the web page as well as in this repository, but they must not be exploited in any way. In other words, it is copyrighted.

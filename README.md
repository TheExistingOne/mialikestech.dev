# mialikestech.dev
This site hosts my portfolio and project blog. It is built using jekyll, jekyll-theme-console, jekyll-feed, jekyll-archive, jekyll-compose, jekyll_picture_tag, and a whole lot of HTML and hope.

For full licensing details see (https://mialikestech.dev/tos/), but the short version is that most code written for this site is under the MIT License and most written content is under CC BY-NC-ND 4.0.


## Local builds
Since it's built on jekyll, this site uses ruby for builds. For best results, I suggest using rbenv for reproducable builds. Once rbenv is installed and working use the following commands to install ruby and it's dependencies:

```
rbenv install 3.3.5
gem install bundler
bundle install
```

Additonally, jekyll_picture_tag requires libvips and corresponding libraries (at minimum you also need libjpeg and having libpng and libwebp won't hurt). On Linux, these can be installed from your package manager. On Mac you can use `brew install vips jpeg webp libpng`. On Windows, download the binary from [libvips.org](https://www.libvips.org/install.html).

Finally run `bundle exec jekyll serve` to test the site.
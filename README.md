# Troubleshooting Trellis in Vue and Nuxt

I'm attempting to get a Trellis graph incorporated into a
[Nuxt](https://nuxt.com/)-based website, but encountered errors with all recent
releases:
* **`0.6.1`** (current `latest` release) and **`0.7.0-rc.13`** &ndash; ESM import
  issue previously reported in https://github.com/sayari-analytics/trellis/issues/81.
* **`0.6.0`** &ndash; `WebGL` fails to import; reported in https://github.com/sayari-analytics/trellis/issues/84

In my investigations I discovered that version `0.6.0` works perfectly fine in
a plain [Vue](https://vuejs.org/) website (without Nuxt), but that both `0.6.1`
and `0.7.0-rc.13` fail in the same manner as Nuxt (ESM import error, detailed
in that app's [README](./vue-trellis-test/README.md#newer-versions-of-trellis)).

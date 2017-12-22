## About Jekyll Plugin not support on Github pages

I've build some static page by GitHub Pages these few days. And I found that I need a plugin name [Jekyll Multiple Languages Plugin](https://github.com/Anthony-Gaudino/jekyll-multiple-languages-plugin) for multiple languages. But when I push it to GitHub. GitHub tell me build fail because my gemfile has unsupport gem.

By [Jekyll official Website](https://jekyllrb.com/docs/plugins/), All Site on GitHub Pages will serve with `--safe` options. So it will not support some custom plugin.

There is a list for [GitHub Pages Dependency versions](https://pages.github.com/versions/).

If you still want to build the GitHub Pages with plugin not on the list. You can use CircleCI. Take a look at this manual [Setting up a Github Pages Project Page with Circle CI](https://github.com/DevProgress/onboarding/wiki/Using-Circle-CI-with-Github-Pages-for-Continuous-Delivery) .

- - - 

## 關於 GitHub Pages 不支援的 Jekyll plugin

最近在使用 Jekyll 製作靜態網站時，用到了 [Jekyll Multiple Languages Plugin](https://github.com/Anthony-Gaudino/jekyll-multiple-languages-plugin) 這個 plugin ，結果一 push GitHub 馬上傳訊息來說我的 Plugin 不支援，才了解原來 GitHub Page 也不是所有 plugin 都吃。

根據 Jekyll 官網[指出](https://jekyllrb.com/docs/plugins/)，所有 Pages 都是經由 `--safe` 選項生成的，未支援或是自己寫的 plugin 都會因為安全性問題而無法作動。

[GitHub Pages Dependency versions](https://pages.github.com/versions/) 這邊有詳列目前支援的 Plugin 。

那如果你需要使用未支援的 Plugin ，可以使用 CircleCI 幫你完成，可以參閱這篇 [Setting up a Github Pages Project Page with Circle CI](https://github.com/DevProgress/onboarding/wiki/Using-Circle-CI-with-Github-Pages-for-Continuous-Delivery)


# [如何通过 JS 运行时快照进行 Web 抓取weekly/issue-213.md at master · ruanyf/weekly
来源：[weekly/issue-213.md at master · ruanyf/weekly](https://github.com/ruanyf/weekly/blob/master/docs/issue-213.md)

## 摘录内容

7、[我所用的自托管应用程序](https://noted.lol/what-are-your-most-used-self-hosted-applications/)（英文）

[![](https://camo.githubusercontent.com/b631a5bf98654aa90e89775f80de2c4827936319c591cebd4d70c3f741b7c0ec/68747470733a2f2f63646e2e6265656b6b612e636f6d2f626c6f67696d672f61737365742f3230323230352f6267323032323035303530392e77656270)
](https://camo.githubusercontent.com/b631a5bf98654aa90e89775f80de2c4827936319c591cebd4d70c3f741b7c0ec/68747470733a2f2f63646e2e6265656b6b612e636f6d2f626c6f67696d672f61737365742f3230323230352f6267323032323035303530392e77656270)

作者介绍了自己在家庭内网托管的所有应用程序，可以当作架设家庭 SaaS 服务的参考。

8、[如何通过 JS 运行时快照进行 Web 抓取](https://www.adriancooney.ie/blog/web-scraping-via-javascript-heap-snapshots)（英文）

[![](https://camo.githubusercontent.com/550f9164b6a15f36ba49a83afffafc66c9f6847980d56b08dcb9df7b05ce91d7/68747470733a2f2f63646e2e6265656b6b612e636f6d2f626c6f67696d672f61737365742f3230323230352f6267323032323035303931372e77656270)
](https://camo.githubusercontent.com/550f9164b6a15f36ba49a83afffafc66c9f6847980d56b08dcb9df7b05ce91d7/68747470733a2f2f63646e2e6265656b6b612e636f6d2f626c6f67696d672f61737365742f3230323230352f6267323032323035303931372e77656270)

很多网页的数据是通过 JS 产生的，这时就特别不便于网页抓取。作者想到了一个很妙的方法，对 JS 运行时生成内存快照，再从快照里面提取网页数据。

## 想法

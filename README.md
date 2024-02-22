<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><p dir="auto"><a href="https://travis-ci.org/baidu/braft" rel="nofollow"><img src="https://camo.githubusercontent.com/73418172bb5720b5f437fb37d0695146a4596fc72d715a6e9bc7868098bf656c/68747470733a2f2f7472617669732d63692e6f72672f62616964752f62726166742e7376673f6272616e63683d6d6173746572" alt="构建状态" data-canonical-src="https://travis-ci.org/baidu/braft.svg?branch=master" style="max-width: 100%;"></a></p>
<hr>
<h1 tabindex="-1" dir="auto"><a id="user-content-overview" class="anchor" aria-hidden="true" tabindex="-1" href="#overview"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></h1>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基于</font><a href="https://github.com/brpc/brpc"><font style="vertical-align: inherit;">brpc的</font></a></font><a href="https://raft.github.io/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">RAFT 共识算法</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><a href="https://en.wikipedia.org/wiki/State_machine_replication" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">复制状态机</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的工业级 C++ 实现</font><font style="vertical-align: inherit;">。</font><font style="vertical-align: inherit;">braft是针对高工作负载、低延迟开销的场景而设计和实现的，考虑到易于理解的概念，以便百度内部的工程师能够独立、正确地构建自己的分布式系统。</font></font><a href="https://github.com/brpc/brpc"><font style="vertical-align: inherit;"></font></a><font style="vertical-align: inherit;"></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">它在百度内部被广泛用于构建高可用系统，例如：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存储系统：键值、块、对象、文件......</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SQL 存储：HA MySQL 集群、分布式事务、NewSQL 系统...</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">元服务：各种主模块、锁服务……</font></font></li>
</ul>
<h1 tabindex="-1" dir="auto"><a id="user-content-getting-started" class="anchor" aria-hidden="true" tabindex="-1" href="#getting-started"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">入门</font></font></h1>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建</font></font><a href="https://github.com/brpc/brpc/blob/master/docs/cn/getting_started.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">brpc</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，它是braft的主要依赖项。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用cmake编译braft</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>$ mkdir bld <span class="pl-k">&amp;&amp;</span> <span class="pl-c1">cd</span> bld <span class="pl-k">&amp;&amp;</span> cmake .. <span class="pl-k">&amp;&amp;</span> make</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="$ mkdir bld &amp;&amp; cd bld &amp;&amp; cmake .. &amp;&amp; make" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="/baidu/braft/blob/master/example"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用例子</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来玩吧</font><font style="vertical-align: inherit;">。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从 vcpkg 安装</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"></font><code>braft</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以使用</font></font><a href="https://github.com/Microsoft/vcpkg"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">vcpkg</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">依赖项管理器下载并安装</font><font style="vertical-align: inherit;">：</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>git clone https://github.com/Microsoft/vcpkg.git
<span class="pl-c1">cd</span> vcpkg
./bootstrap-vcpkg.sh
./vcpkg integrate install
./vcpkg install braft</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="git clone https://github.com/Microsoft/vcpkg.git
cd vcpkg
./bootstrap-vcpkg.sh
./vcpkg integrate install
./vcpkg install braft" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">vcpkg 中的端口</font></font><code>braft</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">由 Microsoft 团队成员和社区贡献者保持最新。</font><font style="vertical-align: inherit;">如果版本已过时，请</font><font style="vertical-align: inherit;">在 vcpkg 存储库上</font></font><a href="https://github.com/Microsoft/vcpkg"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建问题或拉取请求。</font></font></a><font style="vertical-align: inherit;"></font></p>
</li>
</ul>
<h1 tabindex="-1" dir="auto"><a id="user-content-docs" class="anchor" aria-hidden="true" tabindex="-1" href="#docs"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文档</font></font></h1>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">阅读</font></font><a href="/baidu/braft/blob/master/docs/cn/overview.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以了解您可以使用 braf 做什么。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">阅读</font></font><a href="/baidu/braft/blob/master/docs/cn/benchmark.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基准测试</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以快速了解 braft 的性能</font></font></li>
<li><a href="/baidu/braft/blob/master/docs/cn/server.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基于braft构建服务</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/client.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基于braft的接入服务</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/cli.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">命令行工具</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/replication.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">复制模型</font></font></a></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">共识协议：
</font></font><ul dir="auto">
<li><a href="/baidu/braft/blob/master/docs/cn/raft_protocol.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">筏</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/paxos_protocol.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">帕克索斯</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/zab_protocol.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">扎布</font></font></a></li>
<li><a href="/baidu/braft/blob/master/docs/cn/qjm.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">青金明</font></font></a></li>
</ul>
</li>
</ul>
<h1 tabindex="-1" dir="auto"><a id="user-content-discussion" class="anchor" aria-hidden="true" tabindex="-1" href="#discussion"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">讨论</font></font></h1>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">添加微信</font></font><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">zhengpf__87</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">xiongk_2049</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并发送验证信息“ </font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">braft</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> ”，即可邀请您加入讨论组。</font></font></li>
</ul>
</article></div>

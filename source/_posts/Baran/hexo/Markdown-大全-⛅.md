---
title: Markdown 大全 ⛅
tags:
  - Markdown
categories:
  - hexo
cover: 'https://sm.ms/image/j7hbO2zX9eQCJB5'
excerpt: 转载别人的，繁体转为简体
date: 2020-11-03 00:00:00
link:
---

<p>==================</p><p><img src="/img/loading.gif" data-lazy-src="https://cdn.jsdelivr.net/images/blog/hexo/markdown_208x128.png" alt="Markdown"></p><p><strong>注意:</strong> 这是Markdown语法的简体中文版文档。如果您正在寻找英文版<br>文档。请参考：<a target="_blank" rel="noopener" href="http://daringfireball.net/projects/markdown/syntax">Markdown: Syntax</a>。</p><p>这份文件是用 Markdown 写的，你可以<a target="_blank" rel="noopener" href="https://github.com/othree/markdown-syntax-zhtw/blob/master/syntax.md">看看它的原始档</a> 。</p><p>================</p><ul><li><a href="#overview">概述</a><ul><li><a href="#philosophy">哲学</a></li><li><a href="#html">行内 HTML</a></li><li><a href="#autoescape">特殊字元自动转换</a></li></ul></li><li><a href="#block">区块元素</a><ul><li><a href="#p">段落和换行</a></li><li><a href="#header">标题</a></li><li><a href="#blockquote">区块引言</a></li><li><a href="#list">清单</a></li><li><a href="#precode">代码区块</a></li><li><a href="#hr">分隔线</a></li></ul></li><li><a href="#span">区段元素</a><ul><li><a href="#link">连结</a></li><li><a href="#em">强调</a></li><li><a href="#code">代码</a></li><li><a href="#img">图片</a></li></ul></li><li><a href="#misc">其它</a><ul><li><a href="#backslash">跳脱字元</a></li><li><a href="#autolink">自动连结</a></li></ul></li></ul><hr><h2 id="overview">概述</h2><hr><h3 id="philosophy">哲学</h3><p>Markdown 的目标是实现「易读易写」。</p><p>不过最需要强调的便是它的可读性。一份使用 Markdown 格式撰写的文件应该可以直接以纯文字發佈，并且看起来不会像是由许多标签或是格式指令所构成。Markdown 语法受到一些既有 text-to-HTML 格式的影响，包括 [Setext] <a target="_blank" rel="noopener" href="http://docutils.sourceforge.net/mirror/setext.html">1</a>、[atx] <a target="_blank" rel="noopener" href="http://www.aaronsw.com/2002/atx/">2</a>、[Textile] <a target="_blank" rel="noopener" href="http://textism.com/tools/textile/">3</a>、[reStructuredText] <a target="_blank" rel="noopener" href="http://docutils.sourceforge.net/rst.html">4</a>、[Grutatext] <a target="_blank" rel="noopener" href="http://www.triptico.com/software/grutatxt.html">5</a> 和 [EtText] <a target="_blank" rel="noopener" href="http://ettext.taint.org/doc/">6</a>，然而最大灵感来源其实是纯文字的电子邮件格式。</p><p>因此 Markdown 的语法全由标点符号所组成，并经过严谨慎选，是为了让它们看起来就像所要表达的意思。像是在文字两旁加上星号，看起来就像*强调*。Markdown 的清单看起来，嗯，就是清单。假如你有使用过电子邮件，区块引言看起来就真的像是引用一段文字。</p><hr><h3 id="html">行内 HTML</h3><p>Markdown 的语法有个主要的目的：用来作为一种网路内容的<em>写作</em>用语言。</p><p>Markdown 不是要来取代 HTML，甚至也没有要和它相似，它的语法种类不多，只和 HTML 的一部分有关系，重点<em>不是</em>要创造一种更容易写作 HTML 文件的语法，我认为 HTML 已经很容易写了，Markdown 的重点在于，它能让文件更容易阅读、编写。HTML 是一种<em>發佈</em>的格式，Markdown 是一种<em>编写</em>的格式，因此，Markdown 的格式语法只涵盖纯文字可以涵盖的范围。</p><p>不在 Markdown 涵盖范围之外的标签，都可以直接在文件裡面用 HTML 撰写。不需要额外标註这是 HTML 或是 Markdown；只要直接加标签就可以了。</p><p>只有区块元素──比如 <code>&lt;div&gt;</code>、<code>&lt;table&gt;</code>、<code>&lt;pre&gt;</code>、<code>&lt;p&gt;</code> 等标签，必须在前后加上空行，以利与内容区隔。而且这些（元素）的开始与结尾标签，不可以用 tab 或是空白来缩排。Markdown 的产生器有智慧型判断，可以避免在区块标签前后加上没有必要的 <code>&lt;p&gt;</code> 标签。</p><p>举例来说，在 Markdown 文件裡加上一段 HTML 表格：</p><pre><code>This is a regular paragraph.

&lt;table&gt;
    &lt;tr&gt;
        &lt;td&gt;Foo&lt;/td&gt;
    &lt;/tr&gt;
&lt;/table&gt;

This is another regular paragraph.
</code></pre><p>请注意，Markdown 语法在 HTML 区块标签中将不会被进行处理。例如，你无法在 HTML 区块内使用 Markdown 形式的<code>*强调*</code>。</p><p>HTML 的区段标签如 <code>&lt;span&gt;</code>、<code>&lt;cite&gt;</code>、<code>&lt;del&gt;</code> 则不受限制，可以在 Markdown 的段落、清单或是标题裡任意使用。依照个人习惯，甚至可以不用Markdown 格式，而採用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 <code>&lt;a&gt;</code> 或 <code>&lt;img&gt;</code> 标签，可以直接使用这些标签，而不用 Markdown 提供的连结或是影像标示语法。</p><p>HTML 区段标签和区块标签不同，在区段标签的范围内， Markdown 的语法是有效的。</p><hr><h3 id="autoescape">特殊字元自动转换</h3><p>在 HTML 文件中，有两个字元需要特殊处理： <code>&lt;</code> 和 <code>&amp;</code> 。 <code>&lt;</code> 符号用于起始标签，<code>&amp;</code> 符号则用于标记 HTML 实体，如果你只是想要使用这些符号，你必须要使用实体的形式，像是 <code>&amp;lt;</code> 和 <code>&amp;amp;</code>。</p><p><code>&amp;</code> 符号其实很容易让写作网路文件的人感到困扰，如果你要打「AT&amp;T」 ，你必须要写成「<code>AT&amp;amp;T</code>」 ，还得转换网址内的 <code>&amp;</code> 符号，如果你要连结到：</p><pre><code>http://images.google.com/images?num=30&amp;q=larry+bird
</code></pre><p>你必须要把网址转成：</p><pre><code>http://images.google.com/images?num=30&amp;amp;q=larry+bird
</code></pre><p>才能放到连结标签的 <code>href</code> 属性裡。不用说也知道这很容易忘记，这也可能是 HTML 标准检查所检查到的错误中，数量最多的。</p><p>Markdown 允许你直接使用这些符号，但是你要小心跳脱字元的使用，如果你是在HTML 实体中使用 <code>&amp;</code> 符号的话，它不会被转换，而在其它情形下，它则会被转换成 <code>&amp;amp;</code>。所以你如果要在文件中插入一个着作权的符号，你可以这样写：</p><pre><code>&amp;copy;
</code></pre><p>Markdown 将不会对这段文字做修改，但是如果你这样写：</p><pre><code>AT&amp;T
</code></pre><p>Markdown 就会将它转为：</p><pre><code>AT&amp;amp;T
</code></pre><p>类似的状况也会發生在 <code>&lt;</code> 符号上，因为 Markdown 支援 <a href="#html">行内 HTML</a> ，如果你是使用 <code>&lt;</code> 符号作为 HTML 标签使用，那 Markdown 也不会对它做任何转换，但是如果你是写：</p><pre><code>4 &lt; 5
</code></pre><p>Markdown 将会把它转换为：</p><pre><code>4 &amp;lt; 5
</code></pre><p>不过需要注意的是，code 范围内，不论是行内还是区块， <code>&lt;</code> 和 <code>&amp;</code> 两个符号都<em>一定</em>会被转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML code （和 HTML 相对而言， HTML 语法中，你要把所有的 <code>&lt;</code> 和 <code>&amp;</code> 都转换为 HTML 实体，才能在 HTML 文件裡面写出 HTML code。）</p><hr><h2 id="block">区块元素</h2><hr><h3 id="p">段落和换行</h3><p>一个段落是由一个以上相连接的行句组成，而一个以上的空行则会切分出不同的段落（空行的定义是显示上看起来像是空行，便会被视为空行。比方说，若某一行只包含空白和 tab，则该行也会被视为空行），一般的段落不需要用空白或断行缩排。</p><p>「一个以上相连接的行句组成」这句话其实暗示了 Markdown 允许段落内的强迫断行，这个特性和其他大部分的 text-to-HTML 格式不一样（包括 MovableType 的「Convert Line Breaks」选项），其它的格式会把每个断行都转成 <code>&lt;br /&gt;</code> 标签。</p><p>如果你<em>真的</em>想要插入 <code>&lt;br /&gt;</code> 标签的话，在行尾加上两个以上的空白，然后按 enter。</p><p>是的，这确实需要花比较多功夫来插入 <code>&lt;br /&gt;</code> ，但是「每个换行都转换为 <code>&lt;br /&gt;</code>」的方法在 Markdown 中并不适合， Markdown 中 email 式的 <a href="#blockquote">区块引言</a> 和多段落的 <a href="#list">清单</a> 在使用换行来排版的时候，不但更好用，还更好阅读。</p><hr><h3 id="header">标题</h3><p>Markdown 支援两种标题的语法，[Setext] <a target="_blank" rel="noopener" href="http://docutils.sourceforge.net/mirror/setext.html">1</a> 和 [atx] <a target="_blank" rel="noopener" href="http://www.aaronsw.com/2002/atx/">2</a> 形式。</p><p>Setext 形式是用底线的形式，利用 <code>=</code> （最高阶标题）和 <code>-</code> （第二阶标题），例如：</p><pre><code>This is an H1
=============

This is an H2
-------------
</code></pre><p>任何数量的 <code>=</code> 和 <code>-</code> 都可以有效果。</p><p>Atx 形式则是在行首插入 1 到 6 个 <code>#</code> ，对应到标题 1 到 6 阶，例如：</p><pre><code># This is an H1

## This is an H2

###### This is an H6
</code></pre><p>你可以选择性地「关闭」atx 样式的标题，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上 <code>#</code>，而行尾的 <code>#</code> 数量也不用和开头一样（行首的井字数量决定标题的阶数）：</p><pre><code># This is an H1 #

## This is an H2 ##

### This is an H3 ######
</code></pre><hr><h3 id="blockquote">Blockquotes</h3><p>Markdown 使用 email 形式的区块引言，如果你很熟悉如何在 email 信件中引言，你就知道怎么在 Markdown 文件中建立一个区块引言，那会看起来像是你强迫断行，然后在每行的最前面加上 <code>&gt;</code> ：</p><pre><code>&gt; This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
&gt; consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
&gt; Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
&gt; 
&gt; Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
&gt; id sem consectetuer libero luctus adipiscing.
</code></pre><p>Markdown 也允许你只在整个段落的第一行最前面加上 <code>&gt;</code> ：</p><pre><code>&gt; This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

&gt; Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
</code></pre><p>区块引言可以有阶层（例如：引言内的引言），只要根据层数加上不同数量的 <code>&gt;</code> ：</p><pre><code>&gt; This is the first level of quoting.
&gt;
&gt; &gt; This is nested blockquote.
&gt;
&gt; Back to the first level.
</code></pre><p>引言的区块内也可以使用其他的 Markdown 语法，包括标题、清单、代码区块等：</p><pre><code>&gt; ## This is a header.
&gt; 
&gt; 1.   This is the first list item.
&gt; 2.   This is the second list item.
&gt; 
&gt; Here's some example code:
&gt; 
&gt;     return shell_exec("echo $input | $markdown_script");
</code></pre><p>任何标准的文字编辑器都能简单地建立 email 样式的引言，例如 BBEdit ，你可以选取文字后然后从选单中选择<em>增加引言阶层</em>。</p><hr><h3 id="list">清单</h3><p>Markdown 支援有序清单和无序清单。</p><p>无序清单使用星号、加号或是减号作为清单标记：</p><pre><code>*   Red
*   Green
*   Blue
</code></pre><p>等同于：</p><pre><code>+   Red
+   Green
+   Blue
</code></pre><p>也等同于：</p><pre><code>-   Red
-   Green
-   Blue
</code></pre><p>有序清单则使用数字接着一个英文句点：</p><pre><code>1.  Bird
2.  McHale
3.  Parish
</code></pre><p>很重要的一点是，你在清单标记上使用的数字并不会影响输出的 HTML 结果，上面的清单所产生的 HTML 标记为：</p><pre><code>&lt;ol&gt;
&lt;li&gt;Bird&lt;/li&gt;
&lt;li&gt;McHale&lt;/li&gt;
&lt;li&gt;Parish&lt;/li&gt;
&lt;/ol&gt;
</code></pre><p>如果你的清单标记写成：</p><pre><code>1.  Bird
1.  McHale
1.  Parish
</code></pre><p>或甚至是：</p><pre><code>3. Bird
1. McHale
8. Parish
</code></pre><p>你都会得到完全相同的 HTML 输出。重点在于，你可以让 Markdown 文件的清单数字和输出的结果相同，或是你懒一点，你可以完全不用在意数字的正确性。</p><p>如果你使用懒惰的写法，建议第一个项目最好还是从 1. 开始，因为 Markdown 未来可能会支援有序清单的 start 属性。</p><p>清单项目标记通常是放在最左边，但是其实也可以缩排，最多三个空白，项目标记后面则一定要接着至少一个空白或 tab。</p><p>要让清单看起来更漂亮，你可以把内容用固定的缩排整理好：</p><pre><code>*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
</code></pre><p>但是如果你很懒，那也不一定需要：</p><pre><code>*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
</code></pre><p>如果清单项目间用空行分开， Markdown 会把项目的内容在输出时用 <code>&lt;p&gt;</code><br>标签包起来，举例来说：</p><pre><code>*   Bird
*   Magic
</code></pre><p>会被转换为：</p><pre><code>&lt;ul&gt;
&lt;li&gt;Bird&lt;/li&gt;
&lt;li&gt;Magic&lt;/li&gt;
&lt;/ul&gt;
</code></pre><p>但是这个：</p><pre><code>*   Bird

*   Magic
</code></pre><p>会被转换为：</p><pre><code>&lt;ul&gt;
&lt;li&gt;&lt;p&gt;Bird&lt;/p&gt;&lt;/li&gt;
&lt;li&gt;&lt;p&gt;Magic&lt;/p&gt;&lt;/li&gt;
&lt;/ul&gt;
</code></pre><p>清单项目可以包含多个段落，每个项目下的段落都必须缩排 4 个空白或是一个 tab ：</p><pre><code>1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
</code></pre><p>如果你每行都有缩排，看起来会看好很多，当然，再次地，如果你很懒惰，Markdown 也允许：</p><pre><code>*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
</code></pre><p>如果要在清单项目内放进引言，那 <code>&gt;</code> 就需要缩排：</p><pre><code>*   A list item with a blockquote:

    &gt; This is a blockquote
    &gt; inside a list item.
</code></pre><p>如果要放代码区块的话，该区块就需要缩排<em>两次</em>，也就是 8 个空白或是两个 tab：</p><pre><code>*   A list item with a code block:

        &lt;code goes here&gt;
</code></pre><p>当然，项目清单很可能会不小心产生，像是下面这样的写法：</p><pre><code>1986. What a great season.
</code></pre><p>换句话说，也就是在行首出现<em>数字-句点-空白</em>，要避免这样的状况，你可以在句点前面加上反斜线。</p><pre><code>1986\. What a great season.
</code></pre><hr><h3 id="precode">代码区块</h3><p>和程式相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 <code>&lt;pre&gt;</code> 和 <code>&lt;code&gt;</code> 标签来把代码区块包起来。</p><p>要在 Markdown 中建立代码区块很简单，只要简单地缩排 4 个空白或是 1 个 tab 就可以，例如，下面的输入：</p><pre><code>This is a normal paragraph:

    This is a code block.
</code></pre><p>Markdown 会转换成：</p><pre><code>&lt;p&gt;This is a normal paragraph:&lt;/p&gt;

&lt;pre&gt;&lt;code&gt;This is a code block.
&lt;/code&gt;&lt;/pre&gt;
</code></pre><p>这个每行一阶的缩排（4 个空白或是 1 个 tab），都会被移除，例如：</p><pre><code>Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
</code></pre><p>会被转换为：</p><pre><code>&lt;p&gt;Here is an example of AppleScript:&lt;/p&gt;

&lt;pre&gt;&lt;code&gt;tell application "Foo"
    beep
end tell
&lt;/code&gt;&lt;/pre&gt;
</code></pre><p>一个代码区块会一直持续到没有缩排的那一行（或是文件结尾）。</p><p>在代码区块裡面， <code>&amp;</code> 、 <code>&lt;</code> 和 <code>&gt;</code> 会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要複製贴上，再加上缩排就可以了，剩下的 Markdown 都会帮你处理，例如：</p><pre><code>    &lt;div class="footer"&gt;
        &amp;copy; 2004 Foo Corporation
    &lt;/div&gt;
</code></pre><p>会被转换为：</p><pre><code>&lt;pre&gt;&lt;code&gt;&amp;lt;div class="footer"&amp;gt;
    &amp;amp;copy; 2004 Foo Corporation
&amp;lt;/div&amp;gt;
&lt;/code&gt;&lt;/pre&gt;
</code></pre><p>代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号，这表示你可以很容易地以 Markdown 语法撰写 Markdown 语法相关的文件。</p><hr><h3 id="hr">分隔线</h3><p>你可以在一行中用三个或以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号中间插入空白。下面每种写法都可以建立分隔线：</p><pre><code>* * *

***

*****

- - -

---------------------------------------
</code></pre><hr><h2 id="span">区段元素</h2><hr><h3 id="link">连结</h3><p>Markdown 支援两种形式的连结语法： <em>行内</em>和<em>参考</em>两种形式。</p><p>不管是哪一种，连结的文字都是用 [方括号] 来标记。</p><p>要建立一个行内形式的连结，只要在方块括号后面马上接着括号并插入网址连结即可，如果你还想要加上连结的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：</p><pre><code>This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
</code></pre><p>会产生：</p><pre><code>&lt;p&gt;This is &lt;a href="http://example.com/" title="Title"&gt;
an example&lt;/a&gt; inline link.&lt;/p&gt;

&lt;p&gt;&lt;a href="http://example.net/"&gt;This link&lt;/a&gt; has no
title attribute.&lt;/p&gt;
</code></pre><p>如果你是要连结到同样主机的资源，你可以使用相对路径：</p><pre><code>See my [About](/about/) page for details.   
</code></pre><p>参考形式的连结使用另外一个方括号接在连结文字的括号后面，而在第二个方括号裡面要填入用以辨识连结的标签：</p><pre><code>This is [an example][id] reference-style link.
</code></pre><p>你也可以选择性地在两个方括号中间加上空白：</p><pre><code>This is [an example] [id] reference-style link.
</code></pre><p>接着，在文件的任意处，你可以把这个标签的连结内容定义出来：</p><pre><code>[id]: http://example.com/  "Optional Title Here"
</code></pre><p>连结定义的形式为：</p><ul><li>方括号，裡面输入连结的辨识用标签</li><li>接着一个冒号</li><li>接着一个以上的空白或 tab</li><li>接着连结的网址</li><li>选择性地接着 title 内容，可以用单引号、双引号或是括弧包着</li></ul><p>下面这三种连结的定义都是相同：</p><pre><code>[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
</code></pre><p><strong>请注意：</strong>有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的连结 title。</p><p>连结网址也可以用方括号包起来：</p><pre><code>[id]: &lt;http://example.com/&gt;  "Optional Title Here"
</code></pre><p>你也可以把 title 属性放到下一行，也可以加一些缩排，网址太长的话，这样会比较好看：</p><pre><code>[id]: http://example.com/longish/path/to/resource/here
    "Optional Title Here"
</code></pre><p>网址定义只有在产生连结的时候用到，并不会直接出现在文件之中。</p><p>连结辨识标签可以有字母、数字、空白和标点符号，但是并<em>不</em>区分大小写，因此下面两个连结是一样的：</p><pre><code>[link text][a]
[link text][A]
</code></pre><p><em>预设的连结标签</em>功能让你可以省略指定连结标签，这种情形下，连结标签和连结文字会视为相同，要用预设连结标签只要在连结文字后面加上一个空的方括号，如果你要让 “Google” 连结到 google.com，你可以简化成：</p><pre><code>[Google][]
</code></pre><p>然后定义连结内容：</p><pre><code>[Google]: http://google.com/
</code></pre><p>由于连结文字可能包含空白，所以这种简化的标签内也可以包含多个文字：</p><pre><code>Visit [Daring Fireball][] for more information.
</code></pre><p>然后接着定义连结：</p><pre><code>[Daring Fireball]: http://daringfireball.net/
</code></pre><p>连结的定义可以放在文件中的任何一个地方，我比较偏好直接放在连结出现段落的后面，你也可以把它放在文件最后面，就像是註解一样。</p><p>下面是一个参考式连结的范例：</p><pre><code>I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
</code></pre><p>如果改成用连结名称的方式写：</p><pre><code>I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
</code></pre><p>上面两种写法都会产生下面的 HTML。</p><pre><code>&lt;p&gt;I get 10 times more traffic from &lt;a href="http://google.com/"
title="Google"&gt;Google&lt;/a&gt; than from
&lt;a href="http://search.yahoo.com/" title="Yahoo Search"&gt;Yahoo&lt;/a&gt;
or &lt;a href="http://search.msn.com/" title="MSN Search"&gt;MSN&lt;/a&gt;.&lt;/p&gt;
</code></pre><p>下面是用行内形式写的同样一段内容的 Markdown 文件，提供作为比较之用：</p><pre><code>I get 10 times more traffic from [Google](http://google.com/ "Google")
than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
[MSN](http://search.msn.com/ "MSN Search").
</code></pre><p>参考式的连结其实重点不在于它比较好写，而是它比较好读，比较一下上面的范例，使用参考式的文章本身只有 81 个字元，但是用行内形式的连结却会增加到 176 个字元，如果是用纯 HTML 格式来写，会有 234 个字元，在 HTML 格式中，标签比文字还要多。</p><p>使用 Markdown 的参考式连结，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的资讯移到段落文字之外，你就可以增加连结而不让文章的阅读感觉被打断。</p><hr><h3 id="em">强调</h3><p>Markdown 使用星号（<code>*</code>）和底线（<code>_</code>）作为标记强调字词的符号，被 <code>*</code> 或 <code>_</code> 包围的字词会被转成用 <code>&lt;em&gt;</code> 标签包围，用两个 <code>*</code> 或 <code>_</code> 包起来的话，则会被转成 <code>&lt;strong&gt;</code>，例如：</p><pre><code>*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
</code></pre><p>会转成：</p><pre><code>&lt;em&gt;single asterisks&lt;/em&gt;

&lt;em&gt;single underscores&lt;/em&gt;

&lt;strong&gt;double asterisks&lt;/strong&gt;

&lt;strong&gt;double underscores&lt;/strong&gt;
</code></pre><p>你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。</p><p>强调也可以直接插在文字中间：</p><pre><code>un*frigging*believable
</code></pre><p>但是如果你的 <code>*</code> 和 <code>_</code> 两边都有空白的话，它们就只会被当成普通的符号。</p><p>如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：</p><pre><code>\*this text is surrounded by literal asterisks\*
</code></pre><hr><h3 id="code">代码</h3>反引号把它包起来（`` ` ``），例如：<pre><code>Use the `printf()` function.
</code></pre><p>会产生：</p><pre><code>&lt;p&gt;Use the &lt;code&gt;printf()&lt;/code&gt; function.&lt;/p&gt;
</code></pre><p>如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：</p><pre><code>``There is a literal backtick (`) here.``
</code></pre><p>这段语法会产生：</p><pre><code>&lt;p&gt;&lt;code&gt;There is a literal backtick (`) here.&lt;/code&gt;&lt;/p&gt;
</code></pre><p>代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：</p><pre><code>A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
</code></pre><p>会产生：</p><pre><code>&lt;p&gt;A single backtick in a code span: &lt;code&gt;`&lt;/code&gt;&lt;/p&gt;

&lt;p&gt;A backtick-delimited string in a code span: &lt;code&gt;`foo`&lt;/code&gt;&lt;/p&gt;
</code></pre><p>在代码区段内，<code>&amp;</code> 和方括号都会被转成 HTML 实体，这样会比较容易插入 HTML 原始码，Markdown 会把下面这段：</p><pre><code>Please don't use any `&lt;blink&gt;` tags.
</code></pre><p>转为：</p><pre><code>&lt;p&gt;Please don't use any &lt;code&gt;&amp;lt;blink&amp;gt;&lt;/code&gt; tags.&lt;/p&gt;
</code></pre><p>你也可以这样写：</p><pre><code>`&amp;#8212;` is the decimal-encoded equivalent of `&amp;mdash;`.
</code></pre><p>以产生：</p><pre><code>&lt;p&gt;&lt;code&gt;&amp;amp;#8212;&lt;/code&gt; is the decimal-encoded
equivalent of &lt;code&gt;&amp;amp;mdash;&lt;/code&gt;.&lt;/p&gt;
</code></pre><hr><h3 id="img">图片</h3><p>很明显地，要在纯文字应用中设计一个 「自然」的语法来插入图片是有一定难度的。</p><p>Markdown 使用一种和连结很相似的语法来标记图片，同样也允许两种样式： <em>行内</em>和<em>参考</em>。</p><p>行内图片的语法看起来像是：</p><pre><code>![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
</code></pre><p>详细叙述如下：</p><ul><li>一个惊叹号 <code>!</code></li><li>接着一对方括号，裡面放上图片的替代文字</li><li>接着一对普通括号，裡面放上图片的网址，最后还可以用引号包住并加上<br>选择性的 ‘title’ 文字。</li></ul><p>参考式的图片语法则长得像这样：</p><pre><code>![Alt text][id]
</code></pre><p>「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：</p><pre><code>[id]: url/to/image  "Optional title attribute"
</code></pre><p>到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <code>&lt;img&gt;</code> 标签。</p><hr><h2 id="misc">其它</h2><hr><h3 id="autolink">自动连结</h3><p>Markdown 支援比较简短的自动连结形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成连结，连结的文字就和连结位置一样，例如：</p><pre><code>&lt;http://example.com/&gt;
</code></pre><p>Markdown 会转为：</p><pre><code>&lt;a href="http://example.com/"&gt;http://example.com/&lt;/a&gt;
</code></pre><p>自动的邮件连结也很类似，只是 Markdown 会先做一个编码转换的过程，把文字字元转成 16 进位码的 HTML 实体，这样的格式可以溷淆一些不好的信箱地址收集机器人，例如：</p><pre><code>&lt;address@example.com&gt;
</code></pre><p>Markdown 会转成：</p><pre><code>&lt;a href="&amp;#x6D;&amp;#x61;i&amp;#x6C;&amp;#x74;&amp;#x6F;:&amp;#x61;&amp;#x64;&amp;#x64;&amp;#x72;&amp;#x65;
&amp;#115;&amp;#115;&amp;#64;&amp;#101;&amp;#120;&amp;#x61;&amp;#109;&amp;#x70;&amp;#x6C;e&amp;#x2E;&amp;#99;&amp;#111;
&amp;#109;"&gt;&amp;#x61;&amp;#x64;&amp;#x64;&amp;#x72;&amp;#x65;&amp;#115;&amp;#115;&amp;#64;&amp;#101;&amp;#120;&amp;#x61;
&amp;#109;&amp;#x70;&amp;#x6C;e&amp;#x2E;&amp;#99;&amp;#111;&amp;#109;&lt;/a&gt;
</code></pre><p>在浏览器裡面，这段字串会变成一个可以点击的「<a href="mailto:address@example.com">address@example.com</a>」连结。</p><p>（这种作法虽然可以溷淆不少的机器人，但并无法全部挡下来，不过这样也比什么都不做好些。无论如何，公开你的信箱终究会引来广告信件的。）</p><hr><h3 id="backslash">跳脱字元</h3><p>Markdown 可以利用反斜线来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 <code>&lt;em&gt;</code> 标签），你可以在星号的前面加上反斜线：</p><pre><code>\*literal asterisks\*
</code></pre><p>Markdown 支援在下面这些符号前面加上反斜线来帮助插入普通的符号：</p><pre><code>\   反斜线
`   反引号
*   星号
_   底线
{}  大括号
[]  方括号
()  括号
#   井字号
+    加号
-    减号
.   英文句点
!   惊叹号
</code></pre><hr><h3 id="补充"><a href="#补充" class="headerlink" title="补充"></a>补充</h3><p><strong>复选框</strong></p><figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line"><span class="bullet">-</span> [x] 复选框 1</span><br><span class="line"><span class="bullet">-</span> [x] 复选框 2</span><br><span class="line"><span class="bullet">-</span> [ ] 复选框 3</span><br></pre></td></tr></tbody></table></figure><ul><li><input checked="" disabled="" type="checkbox"> 复选框 1</li><li><input checked="" disabled="" type="checkbox"> 复选框 2</li><li><input disabled="" type="checkbox"> 复选框 3</li></ul><hr><p><strong>html 折叠语法</strong></p><details><summary>标题</summary>内容不支持markdown<figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br></pre></td><td class="code"><pre><span class="line"><span class="xml"><span class="tag">&lt;<span class="name">details</span>&gt;</span></span></span><br><span class="line">  <span class="xml"><span class="tag">&lt;<span class="name">summary</span>&gt;</span></span>默认<span class="xml"><span class="tag">&lt;/<span class="name">summary</span>&gt;</span></span></span><br><span class="line">内容不支持markdown</span><br><span class="line"><span class="xml"><span class="tag">&lt;/<span class="name">details</span>&gt;</span></span></span><br></pre></td></tr></tbody></table></figure></details><hr><p><strong>当前皮肤支持选项卡</strong></p><div class="tabs" id="tabsid1"><ul class="nav-tabs"><li class="tab active"><button type="button" data-href="#tabsid1-1">默认</button></li><li class="tab"><button type="button" data-href="#tabsid1-2">预设选择 tabs</button></li><li class="tab"><button type="button" data-href="#tabsid1-3">没有预设值</button></li><li class="tab"><button type="button" data-href="#tabsid1-4">自定义 Tab 名 + 只有 icon + icon 和 Tab 名</button></li></ul><div class="tab-contents"><div class="tab-item-content active" id="tabsid1-1"><figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br><span class="line">11</span><br><span class="line">12</span><br><span class="line">13</span><br></pre></td><td class="code"><pre><span class="line">{% tabs test1 %}</span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 1.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 2.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 3.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line">{% endtabs %}</span><br></pre></td></tr></tbody></table></figure><button type="button" class="tab-to-top" aria-label="scroll to top"><i class="fas fa-arrow-up"></i></button></div><div class="tab-item-content" id="tabsid1-2"><figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br><span class="line">11</span><br><span class="line">12</span><br><span class="line">13</span><br></pre></td><td class="code"><pre><span class="line">{% tabs test2, 3 %}</span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 1.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 2.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 3.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line">{% endtabs %}</span><br></pre></td></tr></tbody></table></figure><button type="button" class="tab-to-top" aria-label="scroll to top"><i class="fas fa-arrow-up"></i></button></div><div class="tab-item-content" id="tabsid1-3"><figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br><span class="line">11</span><br><span class="line">12</span><br><span class="line">13</span><br></pre></td><td class="code"><pre><span class="line">{% tabs test3, -1 %}</span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 1.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 2.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab --&gt;</span></span></span><br><span class="line"><span class="strong">**This is Tab 3.**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line">{% endtabs %}</span><br></pre></td></tr></tbody></table></figure><p><strong>This is Tab 3.</strong></p><button type="button" class="tab-to-top" aria-label="scroll to top"><i class="fas fa-arrow-up"></i></button></div><div class="tab-item-content" id="tabsid1-4"><p><strong>This is Tab 3.</strong></p><figure class="highlight md"><table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br><span class="line">11</span><br><span class="line">12</span><br><span class="line">13</span><br></pre></td><td class="code"><pre><span class="line">{% tabs test4 %}</span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab 第一个Tab --&gt;</span></span></span><br><span class="line"><span class="strong">**tab名字为第一个Tab**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab @fab fa-apple-pay --&gt;</span></span></span><br><span class="line"><span class="strong">**只有图标 没有Tab名字**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line"></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- tab 炸弹@fas fa-bomb --&gt;</span></span></span><br><span class="line"><span class="strong">**名字+icon**</span></span><br><span class="line"><span class="xml"><span class="comment">&lt;!-- endtab --&gt;</span></span></span><br><span class="line">{% endtabs %}</span><br></pre></td></tr></tbody></table></figure><button type="button" class="tab-to-top" aria-label="scroll to top"><i class="fas fa-arrow-up"></i></button></div></div></div><hr>
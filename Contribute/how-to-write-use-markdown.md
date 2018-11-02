---
title: ドキュメントを記述するための Markdown の使用方法
description: この記事では、docs.microsoft.com の記事を記述するために使用される Markdown の基礎と参照情報について説明します。
ms.date: 07/13/2017
ms.openlocfilehash: 6bb8a1fa20957512addb07dda0e68abec4b0a83f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805728"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="d0dd8-103">ドキュメントを記述するための Markdown の使用方法</span><span class="sxs-lookup"><span data-stu-id="d0dd8-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="d0dd8-104">[docs.microsoft.com](http://docs.microsoft.com) の記事は [Markdown](https://daringfireball.net/projects/markdown/) という読みやすく、しかも簡単に学べる軽量マークアップ言語で記述されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="d0dd8-105">そのため、これは急速に業界標準になりました。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="d0dd8-106">Docs のコンテンツは GitHub に格納されるので、[GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) と呼ばれる Markdown の上位セットを使用できます。GFM は一般的な書式要件のための追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="d0dd8-107">さらに、Open Publishing Services (OPS) は Markdown パーサー Markdig を実装しています。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="d0dd8-108">Markdig は GFM との互換性が高く、Docs 固有の機能を実現するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="d0dd8-109">Markdig は高速で、強力で、CommonMark に準拠した、.NET 向けの拡張可能なマークダウン プロセッサーです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="d0dd8-110">優れたコミュニティ サポート</span><span class="sxs-lookup"><span data-stu-id="d0dd8-110">Better community support</span></span>
* <span data-ttu-id="d0dd8-111">優れた標準サポート</span><span class="sxs-lookup"><span data-stu-id="d0dd8-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="d0dd8-112">Markdown の基本</span><span class="sxs-lookup"><span data-stu-id="d0dd8-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="d0dd8-113">見出し</span><span class="sxs-lookup"><span data-stu-id="d0dd8-113">Headings</span></span>

<span data-ttu-id="d0dd8-114">見出しを作成するには、ハッシュ記号 (#) を次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="d0dd8-115">太字や斜体のテキスト</span><span class="sxs-lookup"><span data-stu-id="d0dd8-115">Bold and italic text</span></span>

<span data-ttu-id="d0dd8-116">テキストの書式を**太字**に設定するには、テキストを二重のアスタリスクで囲みます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="d0dd8-117">テキストの書式を*斜体*に設定するには、テキストを一重のアスタリスクで囲みます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="d0dd8-118">テキストの書式を***太字と斜体***の両方に設定するには、テキストを三重のアスタリスクで囲みます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="d0dd8-119">リスト</span><span class="sxs-lookup"><span data-stu-id="d0dd8-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="d0dd8-120">記号付きリスト</span><span class="sxs-lookup"><span data-stu-id="d0dd8-120">Unordered list</span></span>

<span data-ttu-id="d0dd8-121">記号付きリスト/箇条書きリストの書式を設定するには、アスタリスクまたはダッシュを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="d0dd8-122">たとえば、次の Markdown 書式は</span><span class="sxs-lookup"><span data-stu-id="d0dd8-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="d0dd8-123">次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-123">will be rendered as:</span></span>

- <span data-ttu-id="d0dd8-124">List item 1</span><span class="sxs-lookup"><span data-stu-id="d0dd8-124">List item 1</span></span>
- <span data-ttu-id="d0dd8-125">List item 2</span><span class="sxs-lookup"><span data-stu-id="d0dd8-125">List item 2</span></span>
- <span data-ttu-id="d0dd8-126">List item 3</span><span class="sxs-lookup"><span data-stu-id="d0dd8-126">List item 3</span></span>

<span data-ttu-id="d0dd8-127">リストを別のリスト内にネストするには、子リスト アイテムをインデントします。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d0dd8-128">たとえば、次の Markdown 書式は</span><span class="sxs-lookup"><span data-stu-id="d0dd8-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="d0dd8-129">次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-129">will be rendered as:</span></span>

- <span data-ttu-id="d0dd8-130">List item 1</span><span class="sxs-lookup"><span data-stu-id="d0dd8-130">List item 1</span></span>
  - <span data-ttu-id="d0dd8-131">List item A</span><span class="sxs-lookup"><span data-stu-id="d0dd8-131">List item A</span></span>
  - <span data-ttu-id="d0dd8-132">List item B</span><span class="sxs-lookup"><span data-stu-id="d0dd8-132">List item B</span></span>
- <span data-ttu-id="d0dd8-133">List item 2</span><span class="sxs-lookup"><span data-stu-id="d0dd8-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="d0dd8-134">番号付きリスト</span><span class="sxs-lookup"><span data-stu-id="d0dd8-134">Ordered list</span></span>

<span data-ttu-id="d0dd8-135">番号付きリスト/段階的リストの書式を設定するには、対応する番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="d0dd8-136">たとえば、次の Markdown 書式は</span><span class="sxs-lookup"><span data-stu-id="d0dd8-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="d0dd8-137">次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-137">will be rendered as:</span></span>

1. <span data-ttu-id="d0dd8-138">第 1 手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-138">First instruction</span></span>
2. <span data-ttu-id="d0dd8-139">第 2 手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-139">Second instruction</span></span>
3. <span data-ttu-id="d0dd8-140">第 3 手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-140">Third instruction</span></span>

<span data-ttu-id="d0dd8-141">リストを別のリスト内にネストするには、子リスト アイテムをインデントします。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d0dd8-142">たとえば、次の Markdown 書式は</span><span class="sxs-lookup"><span data-stu-id="d0dd8-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="d0dd8-143">次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-143">will be rendered as:</span></span>

1. <span data-ttu-id="d0dd8-144">第 1 手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-144">First instruction</span></span>
   1. <span data-ttu-id="d0dd8-145">下位手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-145">Sub-instruction</span></span>
   2. <span data-ttu-id="d0dd8-146">下位手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-146">Sub-instruction</span></span>
2. <span data-ttu-id="d0dd8-147">第 2 手順</span><span class="sxs-lookup"><span data-stu-id="d0dd8-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="d0dd8-148">表</span><span class="sxs-lookup"><span data-stu-id="d0dd8-148">Tables</span></span>

<span data-ttu-id="d0dd8-149">Markdown の基本仕様には表が含まれていませんが、GFM が表をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="d0dd8-150">パイプ (|) 記号とハイフン記号 (-) を使用して表を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="d0dd8-151">ハイフンは各列のヘッダーを作成し、パイプは各列を区切ります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="d0dd8-152">表が正しくレンダリングされるように、表の前に空の行を 1 つ挿入してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="d0dd8-153">たとえば、次の Markdown 書式は</span><span class="sxs-lookup"><span data-stu-id="d0dd8-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="d0dd8-154">次のようにレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-154">will be rendered as:</span></span>

| <span data-ttu-id="d0dd8-155">Fun</span><span class="sxs-lookup"><span data-stu-id="d0dd8-155">Fun</span></span>                  | <span data-ttu-id="d0dd8-156">With</span><span class="sxs-lookup"><span data-stu-id="d0dd8-156">With</span></span>                 | <span data-ttu-id="d0dd8-157">表</span><span class="sxs-lookup"><span data-stu-id="d0dd8-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="d0dd8-158">left-aligned column</span><span class="sxs-lookup"><span data-stu-id="d0dd8-158">left-aligned column</span></span>  | <span data-ttu-id="d0dd8-159">right-aligned column</span><span class="sxs-lookup"><span data-stu-id="d0dd8-159">right-aligned column</span></span> | <span data-ttu-id="d0dd8-160">centered column</span><span class="sxs-lookup"><span data-stu-id="d0dd8-160">centered column</span></span> |
| <span data-ttu-id="d0dd8-161">$100</span><span class="sxs-lookup"><span data-stu-id="d0dd8-161">$100</span></span>                 | <span data-ttu-id="d0dd8-162">$100</span><span class="sxs-lookup"><span data-stu-id="d0dd8-162">$100</span></span>                 | <span data-ttu-id="d0dd8-163">$100</span><span class="sxs-lookup"><span data-stu-id="d0dd8-163">$100</span></span>            |
| <span data-ttu-id="d0dd8-164">$10</span><span class="sxs-lookup"><span data-stu-id="d0dd8-164">$10</span></span>                  | <span data-ttu-id="d0dd8-165">$10</span><span class="sxs-lookup"><span data-stu-id="d0dd8-165">$10</span></span>                  | <span data-ttu-id="d0dd8-166">$10</span><span class="sxs-lookup"><span data-stu-id="d0dd8-166">$10</span></span>             |
| <span data-ttu-id="d0dd8-167">$1</span><span class="sxs-lookup"><span data-stu-id="d0dd8-167">$1</span></span>                   | <span data-ttu-id="d0dd8-168">$1</span><span class="sxs-lookup"><span data-stu-id="d0dd8-168">$1</span></span>                   | <span data-ttu-id="d0dd8-169">$1</span><span class="sxs-lookup"><span data-stu-id="d0dd8-169">$1</span></span>              |

<span data-ttu-id="d0dd8-170">表作成の詳細については、以下の情報源をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="d0dd8-171">横に長い表の書式設定に役立つ、Markdig の「[表を折り返す機能](#table-wrapping)」。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="d0dd8-172">GitHub の「[Organizing information with tables (表を使用した情報の整理)](https://help.github.com/articles/organizing-information-with-tables/)」。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="d0dd8-173">[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) Web アプリ。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="d0dd8-174">Adam Pritchard 氏の「[Markdown Cheatsheet (Markdown に関する簡易参照ガイド)](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)」。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-174">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="d0dd8-175">Michel Fortin 氏の [Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table) に関するページ。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-175">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="d0dd8-176">[HTML テーブルからマークダウンへの変換](https://jmalarcon.github.io/markdowntables/)。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-176">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="d0dd8-177">リンク</span><span class="sxs-lookup"><span data-stu-id="d0dd8-177">Links</span></span>

<span data-ttu-id="d0dd8-178">インライン リンクの Markdown 構文では、ハイパーリンクされるテキスト部分 `[link text]` の後に、リンク先 URL またはファイル名の部分 `(file-name.md)` が続きます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="d0dd8-179">リンクの詳細については、以下の情報源をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-179">For more information on linking, see:</span></span>

- <span data-ttu-id="d0dd8-180">Markdown のリンクの基本的なサポートについては、[Markdown の構文](https://daringfireball.net/projects/markdown/syntax#link)に関するセクション。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="d0dd8-181">Markdig で提供されるその他のリンク構文の詳細については、このガイドの[リンク](how-to-write-links.md)に関するセクション。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-181">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="d0dd8-182">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="d0dd8-182">Code snippets</span></span>

<span data-ttu-id="d0dd8-183">Markdown では、コード スニペットの配置方法として、文中へのインライン配置と、文と文の間への "フェンスされた" 個別ブロックとしての配置の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="d0dd8-184">詳細については、以下の情報源をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-184">For details, see:</span></span>

- <span data-ttu-id="d0dd8-185">[Markdown のコード ブロックのネイティブ サポート](https://daringfireball.net/projects/markdown/syntax#precode)に関するセクション</span><span class="sxs-lookup"><span data-stu-id="d0dd8-185">[Markdown's native support for code blocks](https://daringfireball.net/projects/markdown/syntax#precode)</span></span>
- <span data-ttu-id="d0dd8-186">[GFM のコード フェンスと構文強調表示のサポート](https://help.github.com/articles/creating-and-highlighting-code-blocks/)に関するページ</span><span class="sxs-lookup"><span data-stu-id="d0dd8-186">[GFM support for code fencing and syntax highlighting](https://help.github.com/articles/creating-and-highlighting-code-blocks/)</span></span>

<span data-ttu-id="d0dd8-187">コード ブロックをフェンスすることで、コード スニペットの構文を強調表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="d0dd8-188">フェンスされたコード ブロックの一般的な書式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="d0dd8-189">冒頭の 3 つのバッククォート (\`) 記号に続くエイリアスは、使用される構文強調表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="d0dd8-190">以下は Docs コンテンツで一般的に使用されるプログラミング言語と、対応するラベルのリストです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="d0dd8-191">これらの言語は、フレンドリ名をサポートし、ほとんどに言語の強調表示機能があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="d0dd8-192">名前</span><span class="sxs-lookup"><span data-stu-id="d0dd8-192">Name</span></span>|<span data-ttu-id="d0dd8-193">Markdown ラベル</span><span class="sxs-lookup"><span data-stu-id="d0dd8-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="d0dd8-194">.NET コンソール</span><span class="sxs-lookup"><span data-stu-id="d0dd8-194">.NET Console</span></span>|<span data-ttu-id="d0dd8-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="d0dd8-195">dotnetcli</span></span>|
|<span data-ttu-id="d0dd8-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-196">ASP.NET (C#)</span></span>|<span data-ttu-id="d0dd8-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="d0dd8-197">aspx-csharp</span></span>|
|<span data-ttu-id="d0dd8-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-198">ASP.NET (VB)</span></span>|<span data-ttu-id="d0dd8-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="d0dd8-199">aspx-vb</span></span>|
|<span data-ttu-id="d0dd8-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="d0dd8-200">AzCopy</span></span>|<span data-ttu-id="d0dd8-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="d0dd8-201">azcopy</span></span>|
|<span data-ttu-id="d0dd8-202">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="d0dd8-202">Azure CLI</span></span>|<span data-ttu-id="d0dd8-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="d0dd8-203">azurecli</span></span>|
|<span data-ttu-id="d0dd8-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0dd8-204">Azure PowerShell</span></span>|<span data-ttu-id="d0dd8-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="d0dd8-205">azurepowershell</span></span>|
|<span data-ttu-id="d0dd8-206">C++</span><span class="sxs-lookup"><span data-stu-id="d0dd8-206">C++</span></span>|<span data-ttu-id="d0dd8-207">cpp</span><span class="sxs-lookup"><span data-stu-id="d0dd8-207">cpp</span></span>|
|<span data-ttu-id="d0dd8-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="d0dd8-208">C++/CX</span></span>|<span data-ttu-id="d0dd8-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="d0dd8-209">cppcx</span></span>|
|<span data-ttu-id="d0dd8-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="d0dd8-210">C++/WinRT</span></span>|<span data-ttu-id="d0dd8-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="d0dd8-211">cppwinrt</span></span>|
|<span data-ttu-id="d0dd8-212">C#</span><span class="sxs-lookup"><span data-stu-id="d0dd8-212">C#</span></span>|<span data-ttu-id="d0dd8-213">csharp</span><span class="sxs-lookup"><span data-stu-id="d0dd8-213">csharp</span></span>|
|<span data-ttu-id="d0dd8-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="d0dd8-214">CSHTML</span></span>|<span data-ttu-id="d0dd8-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="d0dd8-215">cshtml</span></span>|
|<span data-ttu-id="d0dd8-216">DAX</span><span class="sxs-lookup"><span data-stu-id="d0dd8-216">DAX</span></span>|<span data-ttu-id="d0dd8-217">dax</span><span class="sxs-lookup"><span data-stu-id="d0dd8-217">dax</span></span>|
|<span data-ttu-id="d0dd8-218">F#</span><span class="sxs-lookup"><span data-stu-id="d0dd8-218">F#</span></span>|<span data-ttu-id="d0dd8-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="d0dd8-219">fsharp</span></span>|
|<span data-ttu-id="d0dd8-220">Go</span><span class="sxs-lookup"><span data-stu-id="d0dd8-220">Go</span></span>|<span data-ttu-id="d0dd8-221">go</span><span class="sxs-lookup"><span data-stu-id="d0dd8-221">go</span></span>|
|<span data-ttu-id="d0dd8-222">HTML</span><span class="sxs-lookup"><span data-stu-id="d0dd8-222">HTML</span></span>|<span data-ttu-id="d0dd8-223">html</span><span class="sxs-lookup"><span data-stu-id="d0dd8-223">html</span></span>|
|<span data-ttu-id="d0dd8-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="d0dd8-224">HTTP</span></span>|<span data-ttu-id="d0dd8-225">http</span><span class="sxs-lookup"><span data-stu-id="d0dd8-225">http</span></span>|
|<span data-ttu-id="d0dd8-226">Java</span><span class="sxs-lookup"><span data-stu-id="d0dd8-226">Java</span></span>|<span data-ttu-id="d0dd8-227">java</span><span class="sxs-lookup"><span data-stu-id="d0dd8-227">java</span></span>|
|<span data-ttu-id="d0dd8-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d0dd8-228">JavaScript</span></span>|<span data-ttu-id="d0dd8-229">javascript</span><span class="sxs-lookup"><span data-stu-id="d0dd8-229">javascript</span></span>|
|<span data-ttu-id="d0dd8-230">JSON</span><span class="sxs-lookup"><span data-stu-id="d0dd8-230">JSON</span></span>|<span data-ttu-id="d0dd8-231">json</span><span class="sxs-lookup"><span data-stu-id="d0dd8-231">json</span></span>|
|<span data-ttu-id="d0dd8-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="d0dd8-232">Markdown</span></span>|<span data-ttu-id="d0dd8-233">md</span><span class="sxs-lookup"><span data-stu-id="d0dd8-233">md</span></span>|
|<span data-ttu-id="d0dd8-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="d0dd8-234">NodeJS</span></span>|<span data-ttu-id="d0dd8-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="d0dd8-235">nodejs</span></span>|
|<span data-ttu-id="d0dd8-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="d0dd8-236">Objective-C</span></span>|<span data-ttu-id="d0dd8-237">objc</span><span class="sxs-lookup"><span data-stu-id="d0dd8-237">objc</span></span>|
|<span data-ttu-id="d0dd8-238">OData</span><span class="sxs-lookup"><span data-stu-id="d0dd8-238">OData</span></span>|<span data-ttu-id="d0dd8-239">odata</span><span class="sxs-lookup"><span data-stu-id="d0dd8-239">odata</span></span>|
|<span data-ttu-id="d0dd8-240">PHP</span><span class="sxs-lookup"><span data-stu-id="d0dd8-240">PHP</span></span>|<span data-ttu-id="d0dd8-241">php</span><span class="sxs-lookup"><span data-stu-id="d0dd8-241">php</span></span>|
|<span data-ttu-id="d0dd8-242">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="d0dd8-242">Power Apps Formula</span></span>|<span data-ttu-id="d0dd8-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="d0dd8-243">powerappsfl</span></span>|
|<span data-ttu-id="d0dd8-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0dd8-244">PowerShell</span></span>|<span data-ttu-id="d0dd8-245">powershell</span><span class="sxs-lookup"><span data-stu-id="d0dd8-245">powershell</span></span>|
|<span data-ttu-id="d0dd8-246">Python</span><span class="sxs-lookup"><span data-stu-id="d0dd8-246">Python</span></span>|<span data-ttu-id="d0dd8-247">python</span><span class="sxs-lookup"><span data-stu-id="d0dd8-247">python</span></span>|
|<span data-ttu-id="d0dd8-248">Q#</span><span class="sxs-lookup"><span data-stu-id="d0dd8-248">Q#</span></span>|<span data-ttu-id="d0dd8-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="d0dd8-249">qsharp</span></span>|
|<span data-ttu-id="d0dd8-250">R</span><span class="sxs-lookup"><span data-stu-id="d0dd8-250">R</span></span>|<span data-ttu-id="d0dd8-251">r</span><span class="sxs-lookup"><span data-stu-id="d0dd8-251">r</span></span>|
|<span data-ttu-id="d0dd8-252">Ruby</span><span class="sxs-lookup"><span data-stu-id="d0dd8-252">Ruby</span></span>|<span data-ttu-id="d0dd8-253">ruby</span><span class="sxs-lookup"><span data-stu-id="d0dd8-253">ruby</span></span>|
|<span data-ttu-id="d0dd8-254">SQL</span><span class="sxs-lookup"><span data-stu-id="d0dd8-254">SQL</span></span>|<span data-ttu-id="d0dd8-255">sql</span><span class="sxs-lookup"><span data-stu-id="d0dd8-255">sql</span></span>|
|<span data-ttu-id="d0dd8-256">Swift</span><span class="sxs-lookup"><span data-stu-id="d0dd8-256">Swift</span></span>|<span data-ttu-id="d0dd8-257">swift</span><span class="sxs-lookup"><span data-stu-id="d0dd8-257">swift</span></span>|
|<span data-ttu-id="d0dd8-258">TypeScript</span><span class="sxs-lookup"><span data-stu-id="d0dd8-258">TypeScript</span></span>|<span data-ttu-id="d0dd8-259">typescript</span><span class="sxs-lookup"><span data-stu-id="d0dd8-259">typescript</span></span>|
|<span data-ttu-id="d0dd8-260">VB</span><span class="sxs-lookup"><span data-stu-id="d0dd8-260">VB</span></span>|<span data-ttu-id="d0dd8-261">vb</span><span class="sxs-lookup"><span data-stu-id="d0dd8-261">vb</span></span>|
|<span data-ttu-id="d0dd8-262">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="d0dd8-262">VSTS CLI</span></span>|<span data-ttu-id="d0dd8-263">vstscli</span><span class="sxs-lookup"><span data-stu-id="d0dd8-263">vstscli</span></span>|
|<span data-ttu-id="d0dd8-264">XAML</span><span class="sxs-lookup"><span data-stu-id="d0dd8-264">XAML</span></span>|<span data-ttu-id="d0dd8-265">xaml</span><span class="sxs-lookup"><span data-stu-id="d0dd8-265">xaml</span></span>|
|<span data-ttu-id="d0dd8-266">XML</span><span class="sxs-lookup"><span data-stu-id="d0dd8-266">XML</span></span>|<span data-ttu-id="d0dd8-267">xml</span><span class="sxs-lookup"><span data-stu-id="d0dd8-267">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="d0dd8-268">例: C\#</span><span class="sxs-lookup"><span data-stu-id="d0dd8-268">Example: C\#</span></span>

<span data-ttu-id="d0dd8-269">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d0dd8-269">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="d0dd8-270">__レンダー__</span><span class="sxs-lookup"><span data-stu-id="d0dd8-270">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="d0dd8-271">例: SQL</span><span class="sxs-lookup"><span data-stu-id="d0dd8-271">Example: SQL</span></span>

<span data-ttu-id="d0dd8-272">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d0dd8-272">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="d0dd8-273">__レンダー__</span><span class="sxs-lookup"><span data-stu-id="d0dd8-273">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="d0dd8-274">OPS による Markdown のカスタム拡張機能</span><span class="sxs-lookup"><span data-stu-id="d0dd8-274">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="d0dd8-275">Open Publishing Services (OPS) は GitHub Flavored Markdown (GFM) との互換性が非常に高い Markdown パーサー Markdig を実装しています。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-275">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="d0dd8-276">Markdig は Markdown 拡張機能を介していくつかの機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-276">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="d0dd8-277">そのため、完全版の「OPS Authoring Guide」 (OPS オーサリング ガイド) の一部の記事は、参考のためにこのガイドに含まれています </span><span class="sxs-lookup"><span data-stu-id="d0dd8-277">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="d0dd8-278">(たとえば、目次の「Markdig and Markdown extensions」(Markdig と Markdown の拡張機能) と「Code snippets」(コード スニペット) をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-278">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="d0dd8-279">Docs 記事では、段落、リンク、リスト、見出しなど、ほとんどの書式設定に GFM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-279">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="d0dd8-280">記事の高度な書式設定には、次のような Markdig 機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-280">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="d0dd8-281">注ブロック</span><span class="sxs-lookup"><span data-stu-id="d0dd8-281">Note blocks</span></span>
- <span data-ttu-id="d0dd8-282">インクルード</span><span class="sxs-lookup"><span data-stu-id="d0dd8-282">Includes</span></span>
- <span data-ttu-id="d0dd8-283">セレクター</span><span class="sxs-lookup"><span data-stu-id="d0dd8-283">Selectors</span></span>
- <span data-ttu-id="d0dd8-284">埋め込みビデオ</span><span class="sxs-lookup"><span data-stu-id="d0dd8-284">Embedded videos</span></span>
- <span data-ttu-id="d0dd8-285">コード スニペット/サンプル</span><span class="sxs-lookup"><span data-stu-id="d0dd8-285">Code snippets/samples</span></span>

<span data-ttu-id="d0dd8-286">完全なリストについては、目次の「Markdig and Markdown extensions」(Markdig と Markdown の拡張機能) と「Code snippets」(コード スニペット) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-286">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="d0dd8-287">注ブロック</span><span class="sxs-lookup"><span data-stu-id="d0dd8-287">Note blocks</span></span>

<span data-ttu-id="d0dd8-288">特定の内容に注目を集めるには、4 つのタイプの注ブロックから選択できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-288">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="d0dd8-289">NOTE (注意)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-289">NOTE</span></span>
- <span data-ttu-id="d0dd8-290">WARNING (警告)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-290">WARNING</span></span>
- <span data-ttu-id="d0dd8-291">TIP (ヒント)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-291">TIP</span></span>
- <span data-ttu-id="d0dd8-292">IMPORTANT (重要)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-292">IMPORTANT</span></span>

<span data-ttu-id="d0dd8-293">注ブロックによって文章がわかりにくくなることがあるので、概して注ブロックは控えめに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-293">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="d0dd8-294">注ブロックでもコード ブロック、イメージ、リスト、およびリンクがサポートされますが、注ブロックを簡潔でわかりやすくするように心掛けてください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-294">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="d0dd8-295">インクルード</span><span class="sxs-lookup"><span data-stu-id="d0dd8-295">Includes</span></span>

<span data-ttu-id="d0dd8-296">再利用可能なテキスト ファイルまたはイメージ ファイルを記事ファイルにインクルードする必要がある場合は、Markdig のファイル インクルード機能を使用して "インクルード" ファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-296">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="d0dd8-297">この機能は、ビルド時に特定のファイルを記事ファイルにインクルードするように OPS に指示します。これにより、その指定されたファイルは公開記事に含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-297">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="d0dd8-298">コンテンツの再利用に役立つ 3 つのタイプのインクルードがあります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-298">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="d0dd8-299">インライン: 一般的なテキスト スニペットを別の文中にインラインで再利用できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-299">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="d0dd8-300">ブロック: Markdown ファイル全体をブロックとして再利用し、記事のセクション内にネストできます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-300">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="d0dd8-301">イメージ: これは Docs に実装されている標準的なイメージ インクルードの方法です。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-301">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="d0dd8-302">インラインまたはブロックによるインクルードは簡易な Markdown (.md) ファイルにすぎません。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-302">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="d0dd8-303">これにはあらゆる有効な Markdown を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-303">It can contain any valid Markdown.</span></span> <span data-ttu-id="d0dd8-304">すべてのインクルード Markdown ファイルは、リポジトリのルートにある[共通の `/includes` サブディレクトリ](git-github-fundamentals.md#includes-subdirectory)に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-304">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="d0dd8-305">記事が公開されると、インクルードされたファイルはその記事にシームレスに統合されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-305">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="d0dd8-306">インクルードに関する要件と考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-306">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="d0dd8-307">複数の記事に同じテキストを表示する必要があるときには、インクルードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-307">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="d0dd8-308">ブロックによるインクルードは、1 つまたは 2 つの段落、共通の手順、共通のセクションといった分量の多いコンテンツに使用してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-308">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="d0dd8-309">1 つの文よりも小さい場合には、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-309">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="d0dd8-310">インクルードは Markdig 拡張機能に依存するため、GitHub がレンダリングした記事にインクルードはレンダリングされません。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-310">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="d0dd8-311">公開後にのみレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-311">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="d0dd8-312">インクルード内のすべてのテキストの記述には、インクルードを参照する記事内の先行テキストや後続テキストに依存しない完全な文または語句を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-312">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="d0dd8-313">このガイダンスを無視すると、ローカライズされたエクスペリエンスを乱す翻訳不可能な文字列が記事内に発生します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-313">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="d0dd8-314">インクルードをほかのインクルード内に埋め込まないでください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-314">Don't embed includes within other includes.</span></span> <span data-ttu-id="d0dd8-315">それはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-315">They are not supported.</span></span>
- <span data-ttu-id="d0dd8-316">メディア ファイルは、インクルードのサブディレクトリ内にあるメディア フォルダーに配置する必要があります。たとえば、`<repo>`/includes/media フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-316">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="d0dd8-317">メディア ディレクトリのルートにはイメージを配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-317">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="d0dd8-318">イメージがないインクルードの場合は、対応するメディア ディレクトリは不要です。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-318">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="d0dd8-319">通常の記事と同様に、インクルード ファイル間でメディアを共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-319">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="d0dd8-320">インクルードおよび記事ごとに、一意の名前を持つ個別ファイルを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-320">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="d0dd8-321">インクルードに関連するメディア フォルダー内にメディア ファイルを格納してください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-321">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="d0dd8-322">記事の唯一のコンテンツとしてインクルードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-322">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="d0dd8-323">インクルードの目的は、記事内のほかのコンテンツを補完することです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-323">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="d0dd8-324">セレクター</span><span class="sxs-lookup"><span data-stu-id="d0dd8-324">Selectors</span></span>

<span data-ttu-id="d0dd8-325">同じ技術記事の複数のバージョンを記述するときには、複数のテクノロジまたはプラットフォームの実装の違いに対応するために、セレクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-325">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="d0dd8-326">通常、これが最も当てはまるのは、Microsoft の開発者向けのモバイル プラットフォームのコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-326">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="d0dd8-327">現在 Markdig にはシングル セレクターとマルチ セレクターという 2 つのタイプのセレクターがあります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-327">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="d0dd8-328">選択範囲内の各記事に配置されるセレクター Markdown は同じであるため、記事のセレクターをインクルードに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-328">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="d0dd8-329">そのうえで、同じセレクターを使用するすべての記事でそのインクルードを参照できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-329">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="d0dd8-330">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="d0dd8-330">Code snippets</span></span>

<span data-ttu-id="d0dd8-331">Markdig では、コード スニペット拡張機能を使用した記事へのコードの高度なインクルードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-331">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="d0dd8-332">プログラミング言語の選択や構文の色分けといった GFM 機能に基づく高度なレンダリングに加えて、次のような便利な機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-332">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="d0dd8-333">外部リポジトリから集められたコード サンプル/スニペットのインクルード。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-333">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="d0dd8-334">さまざまな言語でのさまざまなバージョンのコード サンプルをタブに表示する UI。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-334">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="d0dd8-335">問題の発見 + トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d0dd8-335">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="d0dd8-336">alt テキスト</span><span class="sxs-lookup"><span data-stu-id="d0dd8-336">Alt text</span></span>

<span data-ttu-id="d0dd8-337">アンダー スコアを含む alt テキストは正しくレンダリングされません。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-337">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="d0dd8-338">たとえば、次のテキストを使用するのではなく、</span><span class="sxs-lookup"><span data-stu-id="d0dd8-338">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="d0dd8-339">次のようにアンダー スコアをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-339">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="d0dd8-340">アポストロフィと引用符</span><span class="sxs-lookup"><span data-stu-id="d0dd8-340">Apostrophes and quotation marks</span></span>

<span data-ttu-id="d0dd8-341">Word から Markdown エディターにコピーしたテキストに、"スマート" (カールした) アポストロフィまたは引用符が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-341">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="d0dd8-342">これらを標準的なアポストロフィや引用符にエンコードまたは変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-342">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span>
<span data-ttu-id="d0dd8-343">そうしないと、ファイルが公開されたときに Itâ€™s のように表示されます</span><span class="sxs-lookup"><span data-stu-id="d0dd8-343">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="d0dd8-344">これらの "スマート" バージョンの記述記号のエンコーディングは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-344">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="d0dd8-345">左 (始め) 二重引用符: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="d0dd8-345">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="d0dd8-346">右 (終わり) 二重引用符: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="d0dd8-346">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="d0dd8-347">右 (終わり) 一重引用符またはアポストロフィ: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="d0dd8-347">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="d0dd8-348">左 (始め) 一重引用符 (あまり使用されません): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="d0dd8-348">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="d0dd8-349">山かっこ</span><span class="sxs-lookup"><span data-stu-id="d0dd8-349">Angle brackets</span></span>

<span data-ttu-id="d0dd8-350">プレースホルダーを示す目的では一般的に山括弧が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-350">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="d0dd8-351">これを (コードではなく) テキストで行うときは、山括弧で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-351">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="d0dd8-352">そうしないと、それらのテキストは Markdown によって HTML タグとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-352">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="d0dd8-353">たとえば、`<script name>` を `&lt;script name&gt;` にエンコードしてください。</span><span class="sxs-lookup"><span data-stu-id="d0dd8-353">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="d0dd8-354">関連項目:</span><span class="sxs-lookup"><span data-stu-id="d0dd8-354">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="d0dd8-355">Markdown に関するリソース</span><span class="sxs-lookup"><span data-stu-id="d0dd8-355">Markdown resources</span></span>

- [<span data-ttu-id="d0dd8-356">Markdown 入門</span><span class="sxs-lookup"><span data-stu-id="d0dd8-356">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="d0dd8-357">Docs の Markdown に関する簡易参照ガイド</span><span class="sxs-lookup"><span data-stu-id="d0dd8-357">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="d0dd8-358">GitHub の Markdown の基本</span><span class="sxs-lookup"><span data-stu-id="d0dd8-358">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="d0dd8-359">Markdown ガイド</span><span class="sxs-lookup"><span data-stu-id="d0dd8-359">The Markdown Guide</span></span>](https://www.markdownguide.org/)

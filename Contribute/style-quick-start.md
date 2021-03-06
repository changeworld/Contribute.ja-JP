---
title: ドキュメント スタイル ガイド - クイック スタート
description: この記事は、docs.microsoft.com を開始するにあたって不可欠なトピックを含む、スタイルで考慮すべき事項についての簡潔なガイドです。
ms.date: 07/25/2017
ms.openlocfilehash: f5c32d3fb71ef3513c68b9c506c823997bfe4d8f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805584"
---
# <a name="docs-style-and-voice-quick-start"></a>ドキュメント スタイルとボイスのクイック スタート

このクイック スタートは、技術的なコンテンツを記述して docs.microsoft.com 上で公開するための簡単なガイドです。 これらのガイドラインは、新しいドキュメントを作成する場合にも、既存のドキュメントを更新する場合にも適用されます。

ベスト プラクティス:

- Microsoft Word にコピーと貼り付けを行ってチェックする必要がある場合でも、記事のスペルと文法をチェックしてください。
- 他の人と 1 対 1 で話している時のような、カジュアルでフレンドリなボイスを使用します。
- シンプルな文を使用します。 読みやすい文章とは、自分が公開するガイダンスを読者がすぐに使用できるということです。

## <a name="use-the-microsoft-voice-principles"></a>Microsoft のボイスの原則の使用

[docs.microsoft.com](https://docs.microsoft.com) の技術コンテンツを記述する場合は、次の原則に従うことが求められます。 常に達成できるわけではありませんが、努力し続けることが必要です。

- **目的に焦点を合わせる**: Microsoft のドキュメントを参照するお客様には、はっきりとした目的があります。 記述を始める前に、対象のお客様とそのお客様が実行しようとしているタスクを明確にします。 次に、その特定のお客様が、その特定のタスクを実行するのに役立つ記事を記述します。
- **一般的な用語を使用する**: 自然言語、ユーザーが使う単語を使用してください。 技術レベルは落とさずに、堅苦しくない言葉を使います。 新しい概念を説明する場合は例を示します。
- **簡潔に記述**: 無駄に単語を使わないでください。 肯定的表現となるようにし、余分な言葉や多くの修飾語を使用しないでください。 文は短く簡潔になるようにします。 記事の要点から外れないようにします。 タスクに修飾語がある場合は、文または段落の先頭に配置します。 また、メモの数は最小限にします。 言葉を省略できるのであれば、スクリーンショットを使用します。
- **目を通しやすい記事にする**: 最も重要な内容を最初に配置します。 長い手順は、セクションを使用して管理しやすい手順グループに分けます (12 個を超える手順は、長すぎる可能性があります)。わかりやすくなるのであれば、スクリーンショットを使用します。
- **共感を示す**: 記事では協力的な表現を使用し、否定は最小限にします。 お客様を苛立たせるであろう箇所を正直に示します。 記事ではお客様にとって重要なことに焦点を合わせるようにします。技術的なことを説くだけにはしないでください。

## <a name="consider-localization-and-machine-translation"></a>ローカライズおよび機械翻訳の考慮

Microsoft の技術的記事はいくつかの言語に翻訳されていますが、特定の市場または地理的な場所に合わせて変更される場合があります。 また、ユーザーは、技術的記事を読むために Web の機械翻訳を使用する場合もあります。 そのため、記述の際には次のガイドラインを考慮します。

- **記事に文法、スペル、または句読点のエラーが含まれないようにする**: これは普段から行う必要があります。 Markdown Pad 2.0 などの一部の Markdown エディターには基本的なスペル チェッカーが備わっていますが、(レンダリングされる HTML) コンテンツを記事から Word に貼り付けることをお勧めします。Word には、より信頼性の高いスペル チェッカーと文法チェッカーが備わっています。
- **できる限り文を短くする**: 重文や句の連鎖があると、翻訳が困難になります。 冗長すぎたり、不自然に感じられたりということがなく文を分割できる場合には、分割します。 いずれにせよ、自然な言葉づかいで記述されていない記事は望ましくありません。
- **シンプルで一貫性のある文構造を使用する**: 翻訳の際に一貫性が向上します。 かっこで囲むことや挿話を避けて、可能な限り文の先頭の近くにサブジェクトを配置します。 公開されているいくつかの記事を確認します。 記事が親しみやすく読みやすいスタイルの場合は、モデルとして使用します。
- **一貫性のある語句および大文字と小文字を使用する**: 繰り返しますが、一貫性は重要です。 文頭にある単語ではない場合、または固有名詞ではない場合は、大文字を使用しないようにします。
- **"スモール ワード" を含める**: 英語では、コンテキストで理解されるため小さくて重要ではないと思われる語句 ("a"、"the"、"that"、"is" など) が、機械翻訳には不可欠です。 必ず含めるようにしてください。

## <a name="other-style-and-voice-issues-to-watch-for"></a>その他の注意すべきスタイルとボイスの問題

- コメントまたは挿話でステップを分割しないでください。
- コード スニペットを含むステップでは、ステップに関する追加情報をコメントとしてコードの中に入れます。 これによって、ユーザーが読む必要があるテキストの全体量が減ります。 また、重要な情報がコード プロジェクトにコピーされることで、ユーザーが後で参照するときにコードの実行内容を思い出せます。
- すべてのタイトルと見出しでは、文頭のみを大文字にします。
- "ログイン" ではなく "サインイン" を使用します。
- 詳細なガイドラインについては、[Microsoft Writing Style Guide (Microsoft ライティング スタイル ガイド)](https://docs.microsoft.com/style-guide/welcome) をご覧ください。

## <a name="localized-documentation"></a>ローカライズされたドキュメント

- ローカライズされたドキュメントの作成に協力する場合は、「[Microsoft ランゲージ ポータル](https://www.microsoft.com/Language/Default.aspx)」を参照してください。
- ローカライズのガイドライン、技術的パブリケーションでの言語のスタイルと用法に関する情報、および市場固有のデータ形式に関する情報については、お使いの言語で[スタイル ガイド](https://www.microsoft.com/Language/StyleGuides)をダウンロードしてください。
- Microsoft のローカライズされた用語については、[製品固有の承認済み用語](https://www.microsoft.com/Language/Default.aspx)を検索するか、お使いの言語で [Microsoft 用語集](https://www.microsoft.com/language/Terminology)をダウンロードしてください。
- ローカライズについて詳しくは、[Microsoft Writing Style Guide (Microsoft ライティング スタイル ガイド)](https://docs.microsoft.com/style-guide/global-communications) の「Global communications」(グローバル コミュニケーション) をご覧ください。

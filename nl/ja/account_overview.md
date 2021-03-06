---

copyright:

  years: 2018
lastupdated: "2018-07-19"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# アカウント階層
{: #overview}

{{site.data.keyword.Bluemix}} アカウントには、相互に作用する多くの要素とシステムが含まれています。 以下の図と各要素の説明は、特定の要素がどのように相関している (結びついている) か、およびアカウントでアクセス権限がどのように機能するかを理解できるようにすることを目的としています。 

<a href="https://console.stage1.bluemix.net/docs/api/content/account/images/account_diagram.svg">
  <img src="images/account_diagram.svg" alt="アカウントの図">
</a>

図の中には、アカウント階層内の要素に関する 2 つの主な概念があり、これらの概念を理解することが重要です。 実線と点線によって、一部の要素が他の要素内に含まれている ( 例えば、ユーザーはアクセス・グループまたは Cloud Foundry の組織に追加される) ことがわかります。 ただし、いくつかの要素は、メンバーシップではなくアクセス権限を提供するために他の要素を操作します。 例えば、ユーザーにはリソース・グループへのアクセス権限が付与されますが、リソース・グループのメンバーにはアクセス・グループの場合と同じ方法では付与されません。 このような概念は、以下のセクションでも説明します。

<dl>
<dt>ユーザー</dt>
<dd>ユーザーはアカウントに招待され、アカウント内のさまざまなリソースへのアクセス権限を付与されます。</dd>
<dt>サービス ID</dt>
<dd>ユーザー ID がユーザーを識別するのと同様の方法で、サービス ID はサービスまたはアプリケーションを識別します。 作成するサービス ID を使用して、{{site.data.keyword.Bluemix_notm}} の外部にあるアプリケーションが {{site.data.keyword.Bluemix_notm}} サービスにアクセスできるようにすることができます。 このサービス ID には、特定のサービスを使用するための許可を制限したり、さまざまなサービスにアクセスするための許可を結合したりする特定のアクセス・ポリシーを割り当てることができます。 サービス ID は特定のユーザーに結合されているわけではないため、ユーザーが組織を辞めてアカウントから削除されるようなことがあっても、サービス ID はそのまま残り、アプリケーションまたはサービスが確実に稼働し続けるようにします。 詳しくは、『[サービス ID の作成と処理](/docs/iam/serviceid.html#serviceids)』を参照してください。</dd>
<dt>サービス・インスタンスまたはリソース</dt>
<dd>{{site.data.keyword.Bluemix_notm}} のサービスは、リソース・グループ・ベースまたは Cloud Foundry ベースです。 リソース・グループに追加して、{{site.data.keyword.Bluemix_notm}} ID 管理およびアクセス管理 (IAM) を使用して管理できるサービス・インスタンスは、リソースと呼ばれます。 Cloud Foundry の組織およびスペースに追加されるサービス・インスタンスは、Cloud Foundry 役割を使用する別のアクセス管理システムを持ちます。 詳しくは、『[リソースとは](/docs/resources/acct_resources.html#resource)』を参照してください。</dd>
<dt>API キー</dt>
<dd>アプリケーション・プログラミング・インターフェース・キー (API キー) は、呼び出し側のアプリケーションまたはユーザーを識別するためにアプリケーション・プログラミング・インターフェース (API) に渡される固有コードです。 ユーザー ID に関連付けられたプラットフォーム API キーと、サービス ID 用に作成できる API キーがあります。 詳しくは、『[API キーの処理](/docs/iam/apikeys.html#manapikey)』を参照してください。</dd>
<dt>アクセス・グループ</dt>
<dd>アクセス・グループを作成して、ユーザーとサービス ID のセットを単一のエンティティーに編成して、許可を簡単に割り当てることができます。 個々のユーザーまたはサービス ID ごとに同じアクセス権限を複数回割り当てるのではなく、単一のポリシーをグループに割り当てることができます。 詳しくは、[アクセス・グループのセットアップ](/docs/iam/groups.html#groups)を参照してください。</dd>
<dt>リソース・グループ</dt>
<dd>リソース・グループは、カスタマイズ可能なグループにアカウント・リソースを編成するための方法で、これにより、複数リソースへのアクセス権限を一度に素早くユーザーに割り当てることができます。 IAM のアクセス制御を使用して管理されるすべてのアカウント・リソースが、アカウント内のリソース・グループに属します。 ユーザーはリソース・グループに追加されませんが、ユーザーにはリソース・グループ内のリソースへのアクセス権限が付与され、ユーザーはリソース・グループを管理することができます。 リソース・グループを管理するためにアクセス権限を付与されたユーザーは、グループ内に新規インスタンスを作成したり、グループを操作するためにその他のユーザーのアクセス権限を管理したり、割り当てられた IAM 役割に基づいてグループ名を編集したりすることができます。 詳しくは、『[リソース・グループの管理](/docs/resources/resourcegroups.html#rgs)』および『[リソースをリソース・グループに編成するためのベスト・プラクティス](/docs/resources/bestpractice_rgs.html#bp_resourcegroups)』を参照してください。</dd>
<dt>Cloud Foundry の組織</dt>
<dd>アカウント所有者または組織管理者は、コンソールの「Cloud Foundry の組織」ページから組織とスペースを追加することができます。 Cloud Foundry の組織とスペースの使用をサポートするサービスをカタログから作成すると、これらのサービスが組織とスペースに追加されます。 組織には、ユーザー、ドメイン、および割り当て量が含まれています。 各組織内には、サービス・インスタンスを含むスペースが追加されます。 詳しくは、『[組織およびスペースの追加](/docs/account/orgs_spaces.html#orgsspacesusers)』を参照してください。</dd>
<dt>Cloud Foundry スペース</dt>
<dd>組織内でスペースを使用して、
アプリケーション、サービス、およびユーザーのセットをグループ化することができます。 スペースは、{{site.data.keyword.Bluemix_notm}} 内の特定の地域に関連付けられます。 デリバリー・ライフサイクルに基づいて、組織内にスペースを作成できます。 例えば、開発環境として dev というスペース、テスト環境として test というスペース、実稼働環境として production というスペースを作成できます。 その後、各スペースにアプリを関連付けることができます。 詳しくは、『[組織およびスペースの追加](/docs/account/orgs_spaces.html#orgsspacesusers)』を参照してください。</dd>
</dl>

この図の別の重要な側面は、アカウント内のリソースへのアクセス権限をアカウント・ユーザーに付与するために使用できる 3 つのタイプのアクセス管理システムの描画です。 

* IAM [アクセス役割](/docs/iam/users_roles.html#iamusermanrol)は、リソース・グループに属するすべてのリソースへのアクセス権限をユーザーに付与するために使用されます。 これらのアクセス役割は、リソース・グループを管理して、リソース・グループに割り当てられる新規サービス・インスタンスを作成するためのアクセス権限をユーザーに付与するためにも使用されます。
* Cloud Foundry [組織とスペースの役割](/docs/iam/cfaccess.html#cfroles)は、Cloud Foundry スペース内にあるサービス・インスタンスへのアクセス権限をユーザーに付与するために使用されます。
* インフラストラクチャーの[カスタマー・ポータル](/docs/customer-portal/cpwhatis.html#customerportal_whatisCP)の許可は、カスタマー・ポータルへのアクセスと、送り状、請求処理、IaaS の構成、IaaS のモニター、IaaS の購入、サポートなどのカスタマー・ポータル内のフィーチャーに対するきめ細かい[許可](/docs/iam/infrastructureaccess.html#infrapermission)をユーザーに付与するために使用可能です。 デバイス・アクセス権限は別のものであり、デバイス自体から処理されます。

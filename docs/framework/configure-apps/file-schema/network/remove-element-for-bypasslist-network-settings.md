---
title: '&lt;削除&gt;bypasslist (ネットワーク設定) の要素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b6c72d9780088fddcaa59e644ff8069afbb4e43d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397099"
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a>&lt;削除&gt;bypasslist (ネットワーク設定) の要素
プロキシ バイ パスの一覧から IP アドレスまたは DNS 名を削除します。  
  
 \<configuration>  
\<system.net>  
\<defaultProxy >  
\<bypasslist >  
\<remove>  
  
## <a name="syntax"></a>構文  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|**属性**|**説明**|  
|-------------------|---------------------|  
|`address`|IP アドレスまたは DNS 名を記述する正規表現。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|**要素**|**説明**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|一連のプロキシを使用しないアドレスを記述する正規表現を提供します。|  
  
## <a name="remarks"></a>Remarks  
 `remove`要素は、IP アドレスまたはプロキシ サーバーをバイパスするアドレスのリストから DNS サーバー名を記述する正規表現を削除します。 アドレスは、構成ファイルで、または構成階層のより高いレベルで既に定義されてです。  
  
 値、`address`属性は、一連の IP アドレスまたはホスト名を記述する正規表現をする必要があります。  
  
 正規表現の詳細についてを参照してください。[.NET framework の正規表現](../../../../../docs/standard/base-types/regular-expressions.md)します。  
  
## <a name="configuration-files"></a>構成ファイル  
 この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。  
  
## <a name="example"></a>例  
 次の例では、adventure-works.com のドメインの以前の定義を削除し、バイパス リストに contoso.com ドメインを追加します。  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [ネットワーク設定スキーマ](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

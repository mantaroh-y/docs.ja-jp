---
title: セキュリティで保護されたセッションに関するセキュリティの検討
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
author: BrucePerlerMS
ms.openlocfilehash: 470ffc007ed73b28beba24bd0eb9c670dea9337d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199971"
---
# <a name="security-considerations-for-secure-sessions"></a>セキュリティで保護されたセッションに関するセキュリティの検討
セキュリティで保護されたセッションを実装する場合に、セキュリティに影響を及ぼす次の項目について考慮する必要があります。 セキュリティに関する考慮事項の詳細については、次を参照してください。[セキュリティに関する考慮事項](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)と[セキュリティのベスト プラクティス](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)します。  
  
## <a name="secure-sessions-and-metadata"></a>セキュリティで保護されたセッションとメタデータ  
 セキュリティで保護されたセッションが確立されたときに、<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>プロパティに設定されて`false`、Windows Communication Foundation (WCF) の送信、`mssp:MustNotSendCancel`アサーションは、Web サービス記述言語 (WSDL) ドキュメントでメタデータの一部として、サービス エンドポイント。 `mssp:MustNotSendCancel` アサーションは、クライアントに対してセキュリティで保護されたセッションのキャンセル要求にサービスが応答しないことを通知します。 ときに、<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>プロパティに設定されて`true`、WCF では生成されませんし、`mssp:MustNotSendCancel`アサーションが WSDL ドキュメントで。 セキュリティで保護されたセッションが必要でなくなった場合、クライアントはサービスに対してキャンセル要求を送る必要があります。 使用して、クライアントが生成されたときに、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)、クライアント コードは、の有無に適切に反応、`mssp:MustNotSendCancel`アサーション。  
  
## <a name="secure-conversations-and-custom-tokens"></a>セキュリティ保護されたメッセージ交換とカスタム トークン  
 WS-SecureConversation 仕様での定義方法に起因する、カスタム トークンと派生キーの混在に関する問題があります。 仕様によればを`wsse:SecurityTokenReference`派生トークンを参照する省略可能な要素です:"`/wsc:DerivedKeyToken/wsse:SecurityTokenReference`この省略可能な要素は、セキュリティ コンテキスト トークン、セキュリティ トークン、または、派生用共有キーやシークレットを指定するために使用します。 指定されていない場合、受信者はメッセージのコンテキストから共有キーを判断できると想定されます。 コンテキストを決定できない場合などのエラー`wsc:UnknownDerivationSource`発生する必要があります"。  
  
 つまり、カスタム トークンを派生させるには、`SecurityTokenReference` 要素にその句型をラップする必要があります。 派生をオフにするオプションもありますが、キーを派生させるオプションが既定となっています。 キーをラップしなかった場合、派生キー トークンのシリアル化は実行されますが、その逆シリアル化を試みると例外がスローされます。  
  
## <a name="see-also"></a>関連項目  
 [方法 : WSFederationHttpBinding のセキュリティで保護されたセッションを無効にする](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [セキュリティの考慮事項](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [セキュリティのベスト プラクティス](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)

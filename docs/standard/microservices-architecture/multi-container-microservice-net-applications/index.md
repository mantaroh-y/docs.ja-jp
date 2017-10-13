---
title: "複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発"
description: ".NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | 複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発"
keywords: "Docker, マイクロサービス, ASP.NET, コンテナー"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 8651254f4550a1a5c6a776ebd2524b5bfe20c546
ms.contentlocale: ja-jp
ms.lasthandoff: 09/05/2017

---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発

*コンテナー化されたマイクロサービス アプリケーションを開発しているということは、複数コンテナーのアプリケーションを構築しているということです。ただし、複数コンテナーのアプリケーションは、単純である可能性があり (3 層アプリケーションなど)、マイクロサービス アーキテクチャを使って構築されない場合があります。*

以前に "マイクロサービス アーキテクチャを構築するときに Docker は必要か?" という疑問を提起しました。 その答えは、明らかに "いいえ" です。 Docker は拡張機能であり、大きな利点を提供できますが、コンテナーおよび Docker はマイクロサービスのハード要件ではありません。 たとえば、簡単なプロセスまたは Docker コンテナーとして実行されているマイクロサービスをサポートする、Azure Service Fabric を使用している場合、Docker の有無にかかわらず、マイクロサービス ベースのアプリケーションを作成できます。

ただし、Docker コンテナーにも基づくマイクロサービス ベースのアプリケーションをデザインおよび開発する方法を知っている場合、その他の単純なアプリケーション モデルをデザインおよび開発することができます。 たとえば、複数コンテナーの手法も必要とする、3 層のアプリケーションをデザインする可能性があります。 そのために、また、マイクロサービス アーキテクチャはコンテナーの世界で重要なトレンドであるため、このセクションでは、Docker コンテナーを使用するマイクロサービス アーキテクチャの実装に注目します。


>[!div class="step-by-step"]
[前へ] (../containerize-net-framework-applications/index.md) [次へ] (microservice-application-design.md)

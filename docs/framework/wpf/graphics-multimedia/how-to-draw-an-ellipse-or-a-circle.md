---
title: '方法 : 楕円または円を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: ddeada8619d1b6c8970f1efb7cca1bc98773d0c5
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003946"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>方法 : 楕円または円を描画する
この例を使用して楕円および真円を描画する方法を示しています、<xref:System.Windows.Shapes.Ellipse>要素。 楕円を描画するために作成、<xref:System.Windows.Shapes.Ellipse>要素を指定し、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>します。 使用してその<xref:System.Windows.Shapes.Shape.Fill%2A>プロパティを指定する、<xref:System.Windows.Media.Brush>楕円の内部を塗りつぶすために使用されます。 使用してその<xref:System.Windows.Shapes.Shape.Stroke%2A>プロパティを指定する、<xref:System.Windows.Media.Brush>楕円のアウトラインを描画するために使用されます。 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>プロパティは、楕円のアウトラインの太さを指定します。  
  
 円を描画するように、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>の<xref:System.Windows.Shapes.Ellipse>互いに等しくない要素。  
  
 次の例では、4 つを描画<xref:System.Windows.Shapes.Ellipse>内の要素を<xref:System.Windows.Controls.Canvas>します。  
  
## <a name="example"></a>例  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 この例を使用しますが、 <xref:System.Windows.Controls.Canvas> 、省略記号を格納することができます使用する楕円要素 (およびその他のすべての図形要素) のいずれか<xref:System.Windows.Controls.Panel>または<xref:System.Windows.Controls.Control>テキスト以外のコンテンツをサポートします。  
  
 この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)

---
title: 查询表达式语法示例：聚合运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: d9d53e91f5252a0ac44822ac6252ce02e9697d33
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130580"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a>查询表达式语法示例：聚合运算符
本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Average%2A>， <xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Max%2A>， <xref:System.Linq.Enumerable.Min%2A>，并<xref:System.Linq.Enumerable.Sum%2A>方法来查询[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)使用查询表达式语法。 这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。  
  
 本主题中的示例使用以下`using` / `Imports`语句：  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a>平均值  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以查找每种样式的产品的平均标价。  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 以获取每个联系人 ID 的平均应付款总计。  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 以针对每个联系人获取具有平均应付款总计的订单。  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a>计数  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Count%2A> 以返回联系人 ID 的列表和每个联系人 ID 所具有的订单数。  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a>示例  
 以下示例按颜色对产品进行分组，并使用 <xref:System.Linq.Enumerable.Count%2A> 以返回每个颜色组中的产品数量。  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a>最大值  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以获取每个联系人 ID 的最大应付款总计。  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以针对每个联系人 ID 获取具有最大应付款总计的订单。  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a>最小值  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以获取每个联系人 ID 的最小应付款总计。  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以针对每个联系人获取具有最小应付款总计的订单。  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a>Sum  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法以获取每个联系人 ID 的应付款总计。  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a>请参阅

- [LINQ to Entities 中的查询](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)

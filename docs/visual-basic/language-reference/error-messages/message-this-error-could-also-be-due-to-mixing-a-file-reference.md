---
title: <message> 此错误也可能是由于文件引用与程序集的项目引用混合使用<assemblyname>
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 951f90a9209ff31896f4426ceb75f05b012897a6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335142"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>\<消息 > 此错误也可能是由于文件引用与程序集的项目引用混合使用\<程序集名称 >
\<消息 > 此错误也可能是由于文件引用与程序集的项目引用混合使用\<程序集名称 >。 在这种情况下，请尝试更换的文件引用 '\<assemblyfilename > 项目中\<projectname1 > 项目引用\<项目名称 2> >。  
  
 你的项目中的代码访问另一个项目的成员，但您的解决方案配置不允许 Visual Basic 编译器来解析引用。  
  
 若要访问另一个程序集中定义的类型，Visual Basic 编译器必须具有对该程序集的引用。 此引用必须单一、明确，不会导致项目之间循环引用。  
  
 **错误 ID:** BC30971  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确定产生最佳程序集引用的项目。 为便于确定，你可以使用文件访问轻松程度和更新频率等条件。  
  
2. 在项目属性中，添加对包含某程序集的项目的引用，该程序集定义正在使用的类型。  
  
## <a name="see-also"></a>请参阅

- [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)

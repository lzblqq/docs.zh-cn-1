---
title: "如何：使用正则表达式搜索字符串（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>如何：使用正则表达式搜索字符串（C# 编程指南）
<xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 类可用于搜索字符串。 从简单搜索到充分利用正则表达式，搜索可以采用不同的复杂模式。 以下是使用 <xref:System.Text.RegularExpressions.Regex> 类执行字符串搜索的两个示例。 有关详细信息，请参阅 [.NET Framework 正则表达式](https://msdn.microsoft.com/library/hs600312)。  
  
## <a name="example"></a>示例  
 以下代码是一个控制台应用程序，用于在数组中执行不区分大小写的简单字符串搜索。 静态方法 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> 执行已给定要搜索的字符串和包含搜索模式的字符串的搜索。 在这种情况下，第三个参数将用于指示应忽略大小写。 有关更多信息，请参见<xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>。  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>示例  
 以下代码是一个控制台应用程序，可使用正则表达式验证数组中每个字符串的格式。 验证要求每个字符串采用电话号码的形式：用短划线分隔成三组数字，前两组包含 3 个数字，而第三组包含 4 个数字。 使用正则表达式 `^\\d{3}-\\d{3}-\\d{4}$` 可以实现此操作。 有关更多信息，请参见[正则表达式语言 - 快速参考](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)。  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [字符串](../../../csharp/programming-guide/strings/index.md)  
 [.NET Framework 正则表达式](https://msdn.microsoft.com/library/hs600312)  
 [正则表达式语言 - 快速参考](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

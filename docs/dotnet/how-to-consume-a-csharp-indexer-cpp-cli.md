---
title: 'Как: использование индексатора C# (C + +/ CLI) | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 00a8164b91a4e483330d4969325a7bd4b6fe6e6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-consume-a-c-indexer-ccli"></a>Практическое руководство. Использование индексатора C# (C++/CLI)
Visual C++ не содержит индексаторов; он индексированных свойств. Чтобы использование индексатора C#, доступа индексатора, как если бы он был индексированного свойства.  
  
 Дополнительные сведения об индексаторах см. в разделе:  
  
-   [Индексаторы](/dotnet/csharp/programming-guide/indexers/index)  
  
## <a name="example"></a>Пример  
 В следующей программе C# определяет индексатор.  
  
```  
// consume_cs_indexers.cs  
// compile with: /target:library  
using System;  
public class IndexerClass {  
   private int [] myArray = new int[100];   
   public int this [int index] {   // Indexer declaration  
      get {  
         // Check the index limits.  
         if (index < 0 || index >= 100)  
            return 0;  
         else  
            return myArray[index];  
      }  
      set {  
         if (!(index < 0 || index >= 100))  
            myArray[index] = value;  
      }  
   }  
}  
/*  
// code to consume the indexer  
public class MainClass {  
   public static void Main() {  
      IndexerClass b = new IndexerClass();  
  
      // Call indexer to initialize elements 3 and 5  
      b[3] = 256;  
      b[5] = 1024;  
      for (int i = 0 ; i <= 10 ; i++)   
         Console.WriteLine("Element #{0} = {1}", i, b[i]);  
   }  
}  
*/  
```  
  
## <a name="example"></a>Пример  
 Эта программа Visual C++ использует индексатор.  
  
```  
// consume_cs_indexers_2.cpp  
// compile with: /clr  
#using "consume_cs_indexers.dll"  
using namespace System;  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->default[0] = 21;  
   for (int i = 0 ; i <= 10 ; i++)  
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);  
}  
```  
  
```Output  
Element #0 = 21  
Element #1 = 0  
Element #2 = 0  
Element #3 = 0  
Element #4 = 0  
Element #5 = 0  
Element #6 = 0  
Element #7 = 0  
Element #8 = 0  
Element #9 = 0  
Element #10 = 0  
```  
  
## <a name="see-also"></a>См. также  
 [Совместимость с другими языками .NET (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)
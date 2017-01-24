---
title: "Практическое руководство. Использование индексатора C# (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++, индексаторы"
  - "индексаторы, использование C#"
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование индексатора C# (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ не содержит индексаторов, однако, имеет индексированные свойства.  Чтобы использовать индексатор C\#, подключитесь к нему таким же образом, как и к индексированному свойству.  
  
 Дополнительные сведения об индексаторах см. в разделе:  
  
-   [Индексаторы](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md)  
  
-   [Практическое руководство. Использование индексированных свойств](../misc/how-to-use-indexed-properties.md)  
  
## Пример  
 Следующая программа C\# определяет индексатор.  
  
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
  
## Пример  
 Программа Visual C\+\+ использует индексатор, определенный программой C\#.  
  
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
  
  **Элемент \#0 \= 21**  
**Элемент №1 \= 0**  
**Элемент №2 \= 0**  
**Элемент №3 \= 0**  
**Элемент №4 \= 0**  
**Элемент №5 \= 0**  
**Элемент №6 \= 0**  
**Элемент №7 \= 0**  
**Элемент №8 \= 0**  
**Элемент №9 \= 0**  
**Элемент №10 \= 0**   
## См. также  
 [Совместимость с другими языками .NET](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)
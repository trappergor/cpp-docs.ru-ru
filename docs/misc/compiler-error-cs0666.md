---
title: "Ошибка компилятора CS0666 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0666"
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ошибка компилятора CS0666
"член": в структуре объявлен новый член с модификатором protected  
  
 Объект [struct](../Topic/struct%20\(C%23%20Reference\).md) не может быть [абстрактным \(abstract\)](../Topic/abstract%20\(C%23%20Reference\).md) и всегда является неявно [запечатанным \(sealed\)](../Topic/sealed%20\(C%23%20Reference\).md). Так как структуры не поддерживают наследование, концепция [защищенного \(protected\)](../Topic/protected%20\(C%23%20Reference\).md) члена в структуре не имеет никакого смысла. Дополнительные сведения см. в разделе [Наследование](../Topic/Inheritance%20\(C%23%20Programming%20Guide\).md).  
  
## Пример  
 В следующем примере возникает ошибка CS0666:  
  
```  
// CS0666.cs class M { static void Main() { } } struct S { protected int x;   // CS0666 }  
```
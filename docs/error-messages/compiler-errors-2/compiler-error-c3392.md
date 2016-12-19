---
title: "Ошибка компилятора C3392 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3392"
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"аргумент\_типа": недопустимый аргумент типа для универсального параметра "параметр" универсального типа "универсальный\_тип"; должен быть открытый конструктор без параметров  
  
 Экземпляр универсального типа был создан неправильно.  Проверьте определение типа.  Дополнительные сведения см. в разделе [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере на языке C\# создается компонент, содержащий универсальный тип, который имеет определенные ограничения, не поддерживаемые при создании универсальных типов в [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]. Дополнительные сведения см. в разделе [Ограничения параметров типа](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
```  
// C3392.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## Пример  
 В следующем примере возникает ошибка C3392:  
  
```  
// C3392_b.cpp // compile with: /clr #using <C3392.dll> ref class R { R(int) {} }; ref class N { N() {} }; value class V {}; ref class N2 { public: N2() {} }; ref class R2 { public: R2() {} }; int main () { GR<R^, V, N^>^ gr1;   // C3392 GR<R^, V, N2^>^ gr1a;   // OK GR<R^, N^, N^>^ gr3;   // C3392 GR<R^, V, N2^>^ gr3a;   // OK GR<R^, V, R^>^ gr4;   // C3392 GR<R^, V, R2^>^ gr4a;   // OK }  
```
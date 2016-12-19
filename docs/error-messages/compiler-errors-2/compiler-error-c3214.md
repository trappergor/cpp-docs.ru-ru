---
title: "Ошибка компилятора C3214 | Microsoft Docs"
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
  - "C3214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3214"
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": недопустимый аргумент типа для универсального параметра "param" универсального типа "универсальный\_тип", не соответствует ограничению "ограничение"  
  
 Для создания экземпляра универсального класса указан тип, который не соответствует ограничению универсального класса.  
  
 Следующий пример приводит к возникновению ошибки C3214:  
  
```  
// C3214.cpp // compile with: /clr interface struct A {}; generic <class T> where T : A ref class C {}; ref class X : public A {}; int main() { C<int>^ c = new C<int>;   // C3214 C<X ^> ^ c2 = new C<X^>;   // OK }  
```
---
title: "Ошибка компилятора C3290 | Microsoft Docs"
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
  - "C3290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3290"
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": тривиальное свойство не может иметь ссылочный тип  
  
 Свойство объявлено неправильно. При объявлении обычного свойства компилятор создает переменную, которую будет обновлять свойство. В классе не может присутствовать ссылочная переменная с отслеживанием.  
  
 Дополнительные сведения см. в разделах [property](../../windows/property-cpp-component-extensions.md) и [Оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3290:  
  
```  
// C3290.cpp // compile with: /clr /c ref struct R {}; ref struct X { R^ mr; property R % y;   // C3290 property R ^ x;   // OK // OK property R% prop { R% get() { return *mr; } void set(R%) {} } }; int main() { X x; R% xp = x.prop; }  
```
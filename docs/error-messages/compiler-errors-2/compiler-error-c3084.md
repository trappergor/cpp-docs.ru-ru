---
title: "Ошибка компилятора C3084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3084"
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C3084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": метод завершения или деструктор не может быть "ключевое\_слово"  
  
 Метод завершения или деструктор был объявлен неправильно.  
  
 Например, деструктор не следует помечать как запечатанный.  Деструктор будет недоступен для производных типов.  Дополнительные сведения см. в разделах [Явные переопределения](../../windows/explicit-overrides-cpp-component-extensions.md) и [Деструкторы и методы завершения в Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Пример  
 При компиляции следующего примера возникнет ошибка C3084.  
  
```  
// C3084.cpp // compile with: /clr /c ref struct R { protected: !R() sealed;   // C3084 !R() abstract;   // C3084 !R(); };  
```
---
title: "Предупреждение компилятора (уровень&#160;1) C4036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4036"
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровень&#160;1) C4036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неименованный "тип" в качестве фактического параметра  
  
 Не задано имя типа для структуры, объединения, перечисления или класса, используемого в качестве фактического параметра. Если вы создаете прототипы функций с помощью параметра [\/Zg](../../build/reference/zg-generate-function-prototypes.md), компилятор выдает это предупреждение и переводит в комментарий этот формальный параметр в созданном прототипе.  
  
 Укажите имя типа, чтобы устранить это предупреждение.  
  
## Пример  
 В следующем примере возникает ошибка C4036.  
  
```  
// C4036.c // compile with: /Zg /W1 // D9035 expected typedef struct { int i; } T; void f(T* t) {}   // C4036 // OK typedef struct MyStruct { int i; } T2; void f2(T2 * t) {}  
```
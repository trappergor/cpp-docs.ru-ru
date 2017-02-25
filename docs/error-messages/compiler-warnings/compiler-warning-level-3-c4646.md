---
title: "Предупреждение компилятора (уровень 3) C4646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4646"
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 3) C4646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция, объявленная с атрибутом \_\_declspec\(noreturn\) имеет тип, отличный от void  
  
 Функция, помеченная модификатором [noreturn](../../cpp/noreturn.md) `__declspec`, должна иметь тип возврата [void](../../cpp/void-cpp.md).  
  
 В следующем примере возникает ошибка C4646.  
  
```  
// C4646.cpp // compile with: /W3 /WX int __declspec(noreturn) TestFunction() {   // C4646  make return type void }  
```
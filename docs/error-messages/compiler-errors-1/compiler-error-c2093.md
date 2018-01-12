---
title: "Ошибка компилятора C2093 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2093
dev_langs: C++
helpviewer_keywords: C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87baed6b2b7058e68afebad7f9f717d8b90d0e8e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2093"></a>Ошибка компилятора C2093
«variable1»: не удается инициализировать с помощью адреса автоматической переменной «variable2»  
  
 При компиляции с параметром [/Za](../../build/reference/za-ze-disable-language-extensions.md), программа пыталась использовать автоматическую переменную в качестве инициализатора.  
  
 Следующий пример приводит к возникновению ошибки C2093:  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```
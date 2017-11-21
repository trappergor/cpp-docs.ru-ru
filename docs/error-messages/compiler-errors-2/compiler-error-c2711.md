---
title: "Ошибка компилятора C2711 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2711
dev_langs: C++
helpviewer_keywords: C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a58a4497e007203119a376e38de82dd91030dfbc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2711"></a>Ошибка компилятора C2711
«функция»: эту функцию невозможно скомпилировать как управляемую, рассмотрите возможность с помощью #pragma неуправляемого  
  
 Некоторые инструкции предотвратит создание MSIL для внешней функции компилятора.  
  
 Следующий пример приводит к возникновению ошибки C2711:  
  
```  
// C2711.cpp  
// compile with: /clr  
// processor: x86  
using namespace System;  
value struct V {  
   static const t = 10;  
};  
  
void bar() {  
   V::t;  
   __asm int 3   // C2711 inline asm can't be compiled managed  
}  
```
---
title: "Ошибка компилятора C2711 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2711
dev_langs:
- C++
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d6b3cc77e88948eaca6aea18568a3992e6aef95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
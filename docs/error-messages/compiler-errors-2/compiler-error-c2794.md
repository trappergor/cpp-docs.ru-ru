---
title: "Ошибка компилятора C2794 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2794
dev_langs: C++
helpviewer_keywords: C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b25829804bf8cb375507550f339022d09951d35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2794"></a>Ошибка компилятора C2794
«функция»: не является членом любой прямой или косвенный базовый класс «класс»  
  
 Предпринята попытка использования [super](../../cpp/super.md) для вызова несуществующей функции-члена.  
  
 Следующий пример приводит к возникновению ошибки C2794  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```
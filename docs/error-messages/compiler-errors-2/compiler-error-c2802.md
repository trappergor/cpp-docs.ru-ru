---
title: "Ошибка компилятора C2802 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2802
dev_langs:
- C++
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: adc1b4178caebe9893727aaf8ff802d6f030e986
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2802"></a>Ошибка компилятора C2802
статический член «оператор» не имеет формальных параметров  
  
 Оператор объявления `static` функция-член должен иметь по крайней мере один параметр.  
  
 Следующий пример приводит к возникновению ошибки C2802:  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```

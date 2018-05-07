---
title: Ошибка компилятора C2688 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2688
dev_langs:
- C++
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd2ebb16acfbc5c7d540e877baab909a950c7f55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2688"></a>Ошибка компилятора C2688
«C2::fgrv»: ковариантные возвращаемые значения с несколькими или виртуальными наследованиями не поддерживаются для функций varargs  
  
 Ковариантные возвращаемые типы не поддерживаются в Visual C++, если функция содержит переменные аргументы.  
  
 Чтобы устранить эту ошибку, либо определите функции, чтобы они не используются переменные-аргументы или сделайте значения возврата одинаковы для всех виртуальных функций.  
  
 Следующий пример приводит к возникновению ошибки C2688:  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```
---
title: "Ошибка компилятора C2688 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2688
dev_langs: C++
helpviewer_keywords: C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eaacdb4c7404dd370de31ad1bca6c07391279584
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
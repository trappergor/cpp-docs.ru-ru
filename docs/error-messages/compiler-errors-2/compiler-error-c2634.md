---
title: "Ошибка компилятора C2634 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2634
dev_langs: C++
helpviewer_keywords: C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d05267b41d1ccad1e67212944a0b82c0dd659091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2634"></a>Ошибка компилятора C2634
"& класс::член": недопустимый указатель на ссылочный член  
  
 Указатель на ссылочный член объявлен.  
  
 Следующий пример приводит к возникновению ошибки C2634:  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```
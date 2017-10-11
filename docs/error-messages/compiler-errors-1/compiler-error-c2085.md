---
title: "Ошибка компилятора C2085 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45805bbea2eca77ae81922088471e99de26be1e4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2085"></a>Ошибка компилятора C2085
«Идентификатор»: отсутствует в списке формальных параметров  
  
 Идентификатор был объявлен в определении функции, но не в списке формальных параметров. (Только в ANSI C)  
  
 Следующий пример приводит к возникновению ошибки C2085:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Возможное решение:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 С точки с запятой функция `func1()` выглядит как определение функции, а не как прототип, поэтому `main` определен внутри `func1()`, ошибки C2085 для идентификатора `main`.

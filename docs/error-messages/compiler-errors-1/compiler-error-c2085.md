---
title: Ошибка компилятора C2085 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0fe489dbdd0934926a056bbc7e5539f40ca1ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
  
 Возможное решение  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 С точки с запятой функция `func1()` выглядит как определение функции, а не как прототип, поэтому `main` определен внутри `func1()`, ошибки C2085 для идентификатора `main`.
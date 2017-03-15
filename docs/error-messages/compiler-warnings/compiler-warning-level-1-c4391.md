---
title: "Предупреждение (уровень 1) C4391 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4391
dev_langs:
- C++
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 81b7e6ba142edb94dd77f4a63c42b245b61ccc45
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4391"></a>Предупреждение компилятора (уровень 1) C4391
«сигнатура»: неверный тип возвращаемого значения для встроенной функции, ожидается «тип»  
  
 В объявлении функции встроенные функции компилятора имел неверный возвращаемый тип. Полученное изображение может работать неправильно.  
  
 Чтобы решить эту проблему, исправьте его объявление или удалить объявление и просто #include соответствующий файл заголовка.  
  
 Следующий пример приводит к возникновению ошибки C4391:  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```

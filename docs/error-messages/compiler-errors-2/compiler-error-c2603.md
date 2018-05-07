---
title: Ошибка компилятора C2603 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2603
dev_langs:
- C++
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68bde3e3fd3319b4c37adcffad4e95aa2544f9fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2603"></a>Ошибка компилятора C2603  
  
> "*функция*": слишком много статических объектов блок области с конструкторами и деструкторами в функции  
  
В версиях до Visual Studio 2015 компилятор Visual C++ или когда [/Zc:threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) указан параметр компилятора, имеется более 31 число статических объектов может иметь в доступном встроенной функции .  
  
Чтобы устранить эту проблему, рекомендуется использовать более новую версию набора инструментов компилятора Visual C++, или если это возможно, удалите параметр компилятора /Zc:threadSafeInit-. Если это невозможно, рассмотрите возможность объединения статических объектов. Если объекты имеют тот же тип, можно использовать статический массив этого типа и ссылаться на отдельные элементы при необходимости.
  
## <a name="example"></a>Пример  
  
Следующий код приводит к возникновению ошибки C2603 и показано, как исправить эту ошибку:  
  
```cpp  
// C2603.cpp  
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };  
extern inline void f1() {  
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;  
    static C C32;   // C2603 Comment this line out to avoid error  
}  
```

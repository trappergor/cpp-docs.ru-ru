---
title: "Ошибка компилятора C2603 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2603
dev_langs:
- C++
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c06c5747a3d785242e8b926fe6e1eaa251a2d8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

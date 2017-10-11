---
title: "C2429 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18fd64199ff043b660bb205199b982ee2843cdcd
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2429"></a>C2429 ошибки компилятора
"*функции языка*«требуется флаг компилятора»*параметр компилятора*"  
  
Функции языка необходимо использовать параметр компилятора, определенные для поддержки  
  
Ошибка C2429: функция языка «nested-namespace-definition» требуется флаг компилятора "/ std:c ++ последнюю" генерируется при попытке определить *составное пространство имен*, пространство имен, которое содержит одно или несколько имен вложенной области видимости пространства имен , начиная с Visual Studio 2015 с обновлением 3. Составные пространства имен определения не допускаются в C++ до C ++ 17. Компилятор поддерживает составное пространство имен определения при [/std: c ++ последнюю](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  

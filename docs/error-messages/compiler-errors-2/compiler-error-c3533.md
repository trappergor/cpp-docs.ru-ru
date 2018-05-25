---
title: Ошибка компилятора C3533 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faaf53d08512559b86c95148bc93e7b3367d2b01
ms.sourcegitcommit: 3bb7c1c0ceeb8012418e2fff9ae5a7db0fff3877
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533
«Тип»: параметр не может иметь тип, содержащий «auto»  
  
 Метод или параметр шаблона не может объявляться с `auto` ключевое слово Если значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) действует параметр компилятора.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалить `auto` ключевое слово из объявления параметра.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает C3533, так как он объявляет параметр функции с `auto` ключевое слово и его компиляции с **/Zc: auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j) {} // C3533  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает C3533 в режим C ++ 14, так как он объявляет параметр шаблона с `auto` ключевое слово и его компиляции с **/Zc: auto**. (В C ++ 17, это допустимое определение шаблона класса с параметром один шаблон не является типом, тип которого определяется.)
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C {}; // C3533  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)

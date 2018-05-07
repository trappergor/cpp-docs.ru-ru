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
ms.openlocfilehash: f184f0459e7ec2251d6ff34e2ee76559fe0dea42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533
«Тип»: параметр не может иметь тип, содержащий «auto»  
  
 Метод или параметр шаблона не может объявляться с `auto` ключевое слово Если значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) действует параметр компилятора.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалить `auto` ключевое слово из объявления параметра.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, так как он объявляет параметр функции с `auto` ключевое слово и его компиляции с **/Zc: auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, так как он объявляет параметр шаблона с `auto` ключевое слово и его компиляции с **/Zc: auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)
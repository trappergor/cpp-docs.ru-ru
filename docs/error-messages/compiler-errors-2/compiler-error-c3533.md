---
title: "Ошибка компилятора C3533 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 73a9efca8245d4d83e8e9cda05c54a502607ea51
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3533"></a>Ошибка компилятора C3533
«Тип»: параметр не может иметь тип, который содержит «auto»  
  
 Параметр метода или шаблона не может объявляться с `auto` ключевое слово Если значение по умолчанию [/Zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) действует параметр компилятора.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалить `auto` ключевое слово из объявления параметра.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, так как он объявляет параметр функции с `auto` ключевое слово и его компилируется с **/Zc: auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, так как он объявляет параметр шаблона с `auto` ключевое слово и его компилируется с **/Zc: auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [/ Zc: auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)

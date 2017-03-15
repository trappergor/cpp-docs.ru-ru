---
title: "Ошибка компилятора C2743 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7420231e64515b556cfe81fc695eda5f75231506
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2743"></a>Ошибка компилятора C2743
«Тип»: невозможно перехватить собственный тип с деструктором __clrcall или конструктор копии  
  
 Модуль, компилированный с **/CLR** выполнил попытку перехвата исключения собственного типа там, где деструктор типа или конструктор копии используют `__clrcall` соглашение о вызовах.  
  
 При компиляции с параметром **/CLR**, обработка исключений ожидает, что функции-члены собственного типа будут [__cdecl](../../cpp/cdecl.md) и не [__clrcall](../../cpp/clrcall.md). Собственные типы с функциями-членами с помощью `__clrcall` соглашение о вызовах, не может быть перехвачено в модуле, скомпилированном с **/CLR**.  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2743.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```

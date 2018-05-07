---
title: Предупреждение (уровень 4) C4460 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4460
dev_langs:
- C++
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3eacdb57dbe3fd657ffb6d1b7612424fe5b4f77
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4460"></a>Предупреждение компилятора (уровень 4) C4460
Оператор WinRT или CLR operator имеет параметр, передаваемый по ссылке. Семантика оператора WinRT или CLR operator отличается от семантики оператора C++ operator. Вы хотели передать по значению?  
  
 Вы передали значение с помощью ссылки определяемому пользователем оператору среды выполнения Windows или среды CLR. Если значение изменяется внутри функции, после вызова функции оно будет назначено возвращаемому значению функции. В стандартном языке C++ измененное значение отражаются после вызова функции.  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C4460 и приводятся сведения по ее устранению.  
  
```  
// C4460.cpp  
// compile with: /W4 /clr   
#include <stdio.h>  
  
public value struct V {  
   static V operator ++(V& me) {   // C4460  
   // try the following line instead  
   // static V operator ++(V me) {  
  
      printf_s(__FUNCSIG__ " called\n");  
      V tmp = me;  
      me.m_i++;  
      return tmp;  
   }  
   int m_i;  
};  
  
int main() {  
   V v;  
   v.m_i = 0;  
  
   printf_s("%d\n", v.m_i);   // Should print 0  
   v++;   // Translates to "v = V::operator ++(v)"  
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning  
}  
```
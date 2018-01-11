---
title: "Предупреждение (уровень 4) C4460 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4460
dev_langs: C++
helpviewer_keywords: C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa925e8d0ef7779f21485cb154b9b9209ce2388e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
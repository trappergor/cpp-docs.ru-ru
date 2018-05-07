---
title: Ошибка компилятора C2893 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db3b71a05ece6b79672d47699dc68e0eb5bb1f60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2893"></a>Ошибка компилятора C2893
Сбой при специализации шаблона функции «имя шаблона»  
  
 Сбой при специализации шаблона функции компилятор. Может быть много причин этой ошибки.  
  
 Как правило для устранения ошибки C2893 проще просмотрите сигнатуру функции и убедитесь, что можно создать экземпляры всех типов.  
  
## <a name="example"></a>Пример  
 C2893 возникает из-за `f`параметр шаблона `T` должен был быть `std::map<int,int>`, но `std::map<int,int>` не имеет члена `data_type` (`T::data_type` не может быть создан с `T = std::map<int,int>`.). Следующий пример приводит к возникновению ошибки C2893.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```
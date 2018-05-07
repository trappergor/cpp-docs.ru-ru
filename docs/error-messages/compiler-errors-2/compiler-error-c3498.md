---
title: Ошибка компилятора C3498 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 913caa8fc73e5fe325a9d17a48b6c2b9ba641546
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3498"></a>Ошибка компилятора C3498
«переменная»: Невозможно записать переменную, имеющую управляемый или WinRTtype  
  
 Нельзя записать переменную, имеющую управляемый тип или тип среды выполнения Windows в лямбда-выражении.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Передайте управляемую переменную или переменную среды выполнения Windows в список параметров лямбда-выражения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3498, так как переменная, имеющая управляемый тип, присутствует в списке записи лямбда-выражения:  
  
```  
// C3498a.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [&s](String ^ r)   
      { return String::Concat(s, r); } (", World!"); // C3498  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример разрешает C3498, передав управляемую переменную `s` в список параметров лямбда-выражения:  
  
```  
// C3498b.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String ^ s = "Hello";  
   [](String ^ s, String ^ r)   
      { return String::Concat(s, r); } (s, ", World!");  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
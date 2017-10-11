---
title: "Ошибка компилятора C3498 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0429b9d21829f772596b6d0fd2c51d72b0924e26
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

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

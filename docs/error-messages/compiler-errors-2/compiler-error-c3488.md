---
title: Ошибка компилятора C3488 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3488
dev_langs:
- C++
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1f872e308c5c80e806ed13d94cd46fb27cdbd47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3488"></a>Ошибка компилятора C3488
var не разрешен, если по умолчанию параметры передаются по ссылке  
  
 Если вы указываете, что для лямбда-выражения по умолчанию используется режим передачи по ссылке, то в предложение передачи этого выражения нельзя передать значение по ссылке.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Не передавайте переменную в предложение передачи явным образом.  
  
-   Не указывайте режим передачи по ссылке в качестве режима по умолчанию.  
  
-   Укажите режим передачи по значению в качестве режима по умолчанию.  
  
-   Передайте переменную в предложение передачи по значению. (Это может изменить поведение лямбда-выражения.)  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере возникает ошибка C3488, так как ссылка на переменную `n` появляется в предложении передачи лямбда-выражения, режим передачи по умолчанию которого — по ссылке.  
  
```  
// C3488a.cpp  
  
int main()  
{  
   int n = 5;  
   [&, &n]() { return n; } (); // C3488  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показаны четыре возможных способа устранения ошибки C3488:  
  
```  
// C3488b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass &n to the capture clause.  
   [&]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-reference as the default capture mode.  
   [&n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-value as the default capture mode.  
   [=, &n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by value to the capture clause.  
   [n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
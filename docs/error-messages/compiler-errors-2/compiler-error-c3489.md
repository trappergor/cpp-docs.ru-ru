---
title: "Ошибка компилятора C3489 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3489
dev_langs: C++
helpviewer_keywords: C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4a0115bbb6d00a4e83d0ae3343b1af1b8024002
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3489"></a>Ошибка компилятора C3489
Переменная "var" обязательна, если режимом по умолчанию является передача параметров по значению  
  
 Если вы указываете, что для лямбда-выражения режимом по умолчанию является передача по значению, то в предложение передачи этого выражения нельзя передать переменную по значению.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Не передавайте переменную в предложение передачи явным образом или  
  
-   не указывайте режим передачи по значению в качестве режима по умолчанию.  
  
-   Укажите в качестве режима по умолчанию режим передачи по ссылке.  
  
-   Передайте переменную в предложение передачи по ссылке. (Это может изменить поведение лямбда-выражения.)  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3489, так как переменная `n` передается по значению в предложение передачи лямбда-выражения, режим передачи по умолчанию которого — по значению:  
  
```  
// C3489a.cpp  
  
int main()  
{  
   int n = 5;  
   [=, n]() { return n; } (); // C3489  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано четыре возможных способа устранения ошибки C3489.  
  
```  
// C3489b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass n to the capture clause.  
   [=]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-value as the default capture mode.  
   [n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-reference as the default capture mode.  
   [&, n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by reference to the capture clause.  
   [&n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
---
title: "Ошибка компилятора C3491 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3491
dev_langs: C++
helpviewer_keywords: C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8c126ae0533424c19fd29ea48dbea8c3d7e8971
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3491"></a>Ошибка компилятора C3491
"var": параметр, передаваемый по значению, не может быть изменен в лямбда-выражении, объявленном как неизменяемое  
  
 Неизменяемое лямбда-выражение не может изменить значение переменной, передаваемой по значению.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Объявите лямбда-выражение с ключевым словом `mutable` или  
  
-   передайте переменную по ссылке в список передачи лямбда-выражения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере возникает ошибка C3491, так как тело неизменяемого лямбда-выражения изменяет передаваемую переменную `m`:  
  
```  
// C3491a.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) { m = n; }(99); // C3491  
}  
```  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере ошибка C3491 устраняется путем объявления лямбда-выражения с ключевым словом `mutable` :  
  
```  
// C3491b.cpp  
  
int main()  
{  
   int m = 55;  
   [m](int n) mutable { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
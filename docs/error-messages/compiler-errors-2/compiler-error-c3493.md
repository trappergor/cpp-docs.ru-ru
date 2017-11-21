---
title: "Ошибка компилятора C3493 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3493
dev_langs: C++
helpviewer_keywords: C3493
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d2336caee3cf2eac6ee748bf40c8cd3f8bf871c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3493"></a>Ошибка компилятора C3493
"переменная" нельзя передать неявно, поскольку не задан режим передачи по умолчанию  
  
 Предложение пустой передачи лямбда-выражения ( `[]`) указывает на то, что лямбда-выражение не передает никаких переменных явно или неявно.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите режим передачи по умолчанию или  
  
-   явно передайте одну или несколько переменных.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере возникает ошибка C3493, так как в нем изменяется внешняя переменная, но указывается предложение пустой передачи.  
  
```  
// C3493a.cpp  
  
int main()  
{  
   int m = 55;  
   [](int n) { m = n; }(99); // C3493  
}  
```  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере ошибка C3493 устраняется путем указания передачи по ссылке в качестве режима передачи по умолчанию.  
  
```  
// C3493b.cpp  
  
int main()  
{  
   int m = 55;  
   [&](int n) { m = n; }(99);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)
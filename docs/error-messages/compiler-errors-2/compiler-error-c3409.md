---
title: "Ошибка компилятора C3409 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3409
dev_langs: C++
helpviewer_keywords: C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22b179a74701cb79100285aeb426bb28531730b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3409"></a>Ошибка компилятора C3409
пустой блок атрибута не допускается  
  
 Квадратные скобки интерпретировались компилятором как [атрибута](../../windows/cpp-attributes-reference.md) блок, однако атрибуты не найдены.  
  
 Компилятор может создать эту ошибку, при использовании квадратные скобки в определении лямбда-выражения. Эта ошибка возникает, когда компилятор не может определить, являются ли квадратные скобки частью определения лямбда-выражения или частью блока атрибутов. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если квадратные скобки являются частью блока атрибутов:  
  
    1.  Укажите один или несколько атрибутов в блоке атрибутов.  
  
    2.  Удалите блок атрибутов.  
  
2.  Если квадратные скобки являются частью лямбда-выражения:  
  
    1.  Убедитесь в том, что лямбда-выражении соблюдаются правила синтаксиса.  
  
         Дополнительные сведения о синтаксисе лямбда-выражений см. в разделе [синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md).  
  
    2.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3409.  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3409 поскольку лямбда-выражение использует `mutable` спецификации, но не предоставляет список параметров. Компилятор не может определить, являются ли квадратные скобки частью определения лямбда-выражения или частью блока атрибутов.  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [атрибут](../../windows/cpp-attributes-reference.md)   
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)   
 [Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)
---
title: __noop | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __noop_cpp
- __noop
dev_langs:
- C++
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14d7ab3f1a61dc0644bf5683376ac676fbfcd6b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="noop"></a>__noop
**Блок, относящийся только к системам Microsoft**  
  
 `__noop` Встроенный Указывает игнорирование функции и проанализировать список аргументов, но не удается создать код для аргументов. Он предназначен для использования в отладки глобальных функций, принимающих переменное число аргументов.  
  
 Компилятор преобразует `__noop` встроенными в 0, во время компиляции.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как использовать `__noop`.  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
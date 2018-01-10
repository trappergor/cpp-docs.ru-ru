---
title: "Макросы с переменным числом аргументов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf4d669f1a716751d02e06c2c52de5df5128b1a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="variadic-macros"></a>Макрос со списками аргументов переменных
Макросы с переменным числом аргументов напоминают собой функции и могут содержать переменное число аргументов.  
  
## <a name="remarks"></a>Примечания  
 Чтобы использовать макросы с переменным числом аргументов, кнопку с многоточием могут быть указаны как окончательный формального аргумента в определении макроса и идентификатор замены `__VA_ARGS__` может использоваться для вставки дополнительных аргументов в определении.  `__VA_ARGS__`заменяются все аргументы, которые совпадают с многоточием, включая запятые между ними.  
  
 В стандарте C указывается, что многоточию должен быть передан по меньшей мере один аргумент, чтобы в конце разрешенного макросом выражения не находилась запятая.  Реализация Visual C++ подавляет запятую в конце выражения, если многоточию не переданы аргументы.  
  
## <a name="example"></a>Пример  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
```  
  
## <a name="see-also"></a>См. также  
 [Макросы (C/C++)](../preprocessor/macros-c-cpp.md)
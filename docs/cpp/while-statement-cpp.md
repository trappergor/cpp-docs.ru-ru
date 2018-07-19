---
title: Оператор while (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc826b588f133abb93c9942e7907dd8b0fce9574
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944244"
---
# <a name="while-statement-c"></a>Оператор while (C++)
Выполняет *statement* (инструкции) циклически, пока *expression* (выражение) не станет равно нулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Примечания  
 Тест на *выражение* выполняется перед каждым выполнением цикла; таким образом, **хотя** цикл выполняется ноль или более раз. Выражение *expression* должно иметь целочисленный тип, тип указателя или тип класса с однозначным преобразованием в целочисленный тип или тип указателя.  
  
 Объект **хотя** цикл прерывается, если [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), или [возвращают](../cpp/return-statement-cpp.md) в операторе выполняется тело. Используйте [по-прежнему](../cpp/continue-statement-cpp.md) чтобы прервать текущую итерацию без выхода из **хотя** цикла. **по-прежнему** передает управление следующей итерации **хотя** цикла.  
  
 В следующем коде используется **хотя** цикла, чтобы удалить конечные символы подчеркивания из строки:  
  
```cpp 
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 Условие завершения вычисляется в начале цикла. Если символов подчеркивания в конце строки нет, цикл никогда не выполняется.  
  
## <a name="see-also"></a>См. также  
 [Операторы итерации](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор do-while (C++)](../cpp/do-while-statement-cpp.md)   
 [Оператор for (C++)](../cpp/for-statement-cpp.md)   
 [Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md)
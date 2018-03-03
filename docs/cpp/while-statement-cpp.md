---
title: "While-оператор (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e93d31457beb3c1546b55d303fd71566176a9367
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="while-statement-c"></a>Оператор while (C++)
Выполняет *инструкции* пока *выражение* равняется нулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      while ( expression )  
   statement  
```  
  
## <a name="remarks"></a>Примечания  
 Проверка *выражение* выполняется перед каждым выполнением цикла; таким образом, `while` цикл выполняется ноль или более раз. *выражение* должен иметь целочисленный тип, тип указателя или тип класса с однозначным преобразованием в целочисленный тип или тип указателя.  
  
 Объект `while` цикла может также прерываться, когда [разрыв](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), или [возвращают](../cpp/return-statement-cpp.md) внутри оператора выполняется тело. Используйте [Продолжить](../cpp/continue-statement-cpp.md) чтобы прервать текущую итерацию без выхода `while` цикла. **Продолжить** передает управление следующей итерации цикла `while` цикла.  
  
 В следующем коде цикл `while` используется для усечения символов подчеркивания в конце строки.  
  
```  
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
 [Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
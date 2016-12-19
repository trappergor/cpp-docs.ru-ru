---
title: "Макрос _STATIC_ASSERT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_STATIC_ASSERT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_STATIC_ASSERT - макрос"
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Макрос _STATIC_ASSERT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляют выражение во время компиляции и генерируют ошибку, когда результат равен `FALSE`.  
  
## Синтаксис  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### Параметры  
 `booleanExpression`  
 Выражение \(включая указатели\), результат вычисления которого не является нулем \(`TRUE`\) или является нулем \(`FALSE`\).  
  
## Заметки  
 Этот макрос похож на [макросы \_ASSERT и \_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), за исключением того, что `booleanExpression` вычисляется во время компиляции, а не во время выполнения.  Если `booleanExpression` равен `FALSE` \(0\), то [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) создается.  
  
## Пример  
 В этом примере мы проверяем, является ли `sizeof` `int` большим или равным 2 байтам и является ли `sizeof` `long` равным одному байту.  Программа не будет компилироваться и сгенерирует [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md), поскольку `long` больше 1 байта.  
  
```  
// crt__static_assert.c  
  
#include <crtdbg.h>  
#include <stdio.h>  
  
_STATIC_ASSERT(sizeof(int) >= 2);  
_STATIC_ASSERT(sizeof(long) == 1);  // C2466  
  
int main()  
{  
    printf("I am sure that sizeof(int) will be >= 2: %d\n",  
        sizeof(int));  
    printf("I am not so sure that sizeof(long) == 1: %d\n",  
        sizeof(long));  
}  
```  
  
## Требования  
  
|Макрос|Обязательный заголовок|  
|------------|----------------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h\>|  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Макросы \_ASSERT, \_ASSERTE, \_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)
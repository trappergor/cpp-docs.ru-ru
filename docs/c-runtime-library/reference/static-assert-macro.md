---
title: "Макрос _STATIC_ASSERT | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _STATIC_ASSERT
dev_langs:
- C++
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f62f2f2f5a0d78a0b77cb21d869be209d9293bd0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="staticassert-macro"></a>Макрос _STATIC_ASSERT
Вычисляет выражение во время компиляции и выдает ошибку, если результат — `FALSE`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_STATIC_ASSERT(  
    booleanExpression  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Выражение (включая указатели), результат вычисления которого отличен от нуля (`TRUE`) или равен нулю (`FALSE`).  
  
## <a name="remarks"></a>Примечания  
 Этот макрос напоминает [макросы _ASSERT и _ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), за исключением того, что `booleanExpression` вычисляется во время компиляции, а не во время выполнения. Если результат вычисления `booleanExpression` равен `FALSE` (0), создается [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md).  
  
## <a name="example"></a>Пример  
 В этом примере проверяется, является ли `sizeof` `int` больше или равно двум байтам и равно ли значение `sizeof` `long` одному байту. Программа не будет скомпилирована, будет создана [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md), так как `long` превышает 1 байт.  
  
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
  
## <a name="requirements"></a>Требования  
  
|Макрос|Обязательный заголовок|  
|-----------|---------------------|  
|`_STATIC_ASSERT`|\<crtdbg.h>|  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)
---
title: Макрос _STATIC_ASSERT | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8eda76666679b133b2d5486d21cd4c8e24d1fdf3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105087"
---
# <a name="staticassert-macro"></a>Макрос _STATIC_ASSERT

Вычисляет выражение во время компиляции и выдают ошибку при выполнении в результате **FALSE**.

## <a name="syntax"></a>Синтаксис

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Параметры

*booleanExpression*<br/>
Выражение (включая указатели), которое возвращает ненулевое значение (**TRUE**) или 0 (**FALSE**).

## <a name="remarks"></a>Примечания

Этот макрос напоминает [макросы _ASSERT и _ASSERTE](assert-asserte-assert-expr-macros.md), за исключением того, что *booleanExpression* вычисляется во время компиляции, а не во время выполнения. Если *booleanExpression* принимает значение **FALSE** (0), [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) создается.

## <a name="example"></a>Пример

В этом примере мы проверяем ли [sizeof](../../c-language/sizeof-operator-c.md) **int** больше или равно двум байтам и был ли [sizeof](../../c-language/sizeof-operator-c.md) **long** равен 1 байту. Программа не будет компилироваться и генерирует [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) поскольку **long** больше, чем 1 байт.

```C
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
|**_STATIC_ASSERT**|\<crtdbg.h>|

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR](assert-asserte-assert-expr-macros.md)<br/>

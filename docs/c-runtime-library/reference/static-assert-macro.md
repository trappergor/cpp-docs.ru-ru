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
ms.openlocfilehash: bbbab8314a038d796ebd1a13342f3054e59f3e68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407370"
---
# <a name="staticassert-macro"></a>Макрос _STATIC_ASSERT

Вычисление выражения во время компиляции и выдает ошибку, если результат **FALSE**.

## <a name="syntax"></a>Синтаксис

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Параметры

*booleanExpression* (включая указатели) выражение, которое возвращает ненулевое значение (**TRUE**) или 0 (**FALSE**).

## <a name="remarks"></a>Примечания

Этот макрос напоминает [макросы _ASSERT и _ASSERTE](assert-asserte-assert-expr-macros.md), за исключением того, что *booleanExpression* вычисляется во время компиляции, а не во время выполнения. Если *booleanExpression* равен **FALSE** (0), [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) создается.

## <a name="example"></a>Пример

В этом примере мы проверяем ли [sizeof](../../c-language/sizeof-operator-c.md) **int** больше или равно 2 байта и ли [sizeof](../../c-language/sizeof-operator-c.md) **длинные** — 1 байт. Программа не будет компилироваться, и создавать [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) из-за **длинные** больше, чем 1 байт.

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

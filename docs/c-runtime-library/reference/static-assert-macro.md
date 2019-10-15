---
title: Макрос _STATIC_ASSERT
ms.date: 11/04/2016
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _STATIC_ASSERT
helpviewer_keywords:
- _STATIC_ASSERT macro
ms.assetid: 89b0350c-2c2f-4be6-9786-8b1f0780a5da
ms.openlocfilehash: ac609fc7af937b6f56cd5b310341409187df7de4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957931"
---
# <a name="_static_assert-macro"></a>Макрос _STATIC_ASSERT

Вычисление выражения во время компиляции и создание ошибки, когда результат равен **false**.

## <a name="syntax"></a>Синтаксис

```C
_STATIC_ASSERT(
    booleanExpression
);
```

### <a name="parameters"></a>Параметры

*булеанекспрессион*<br/>
Выражение (включая указатели), результатом вычисления которого является ненулевое**значение (true**) или 0 (**false**).

## <a name="remarks"></a>Примечания

Этот макрос напоминает [макросы _ASSERT и _ASSERTE](assert-asserte-assert-expr-macros.md), за исключением того, что *булеанекспрессион* вычисляется во время компиляции, а не в среде выполнения. Если *булеанекспрессион* принимает **значение false** (0), создается [Ошибка компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) .

## <a name="example"></a>Пример

В этом примере мы проверяем, является ли значение [sizeof](../../c-language/sizeof-operator-c.md) **int** большим или равным 2 байтами и является ли значение [sizeof](../../c-language/sizeof-operator-c.md) **длинным** 1 байтом. Программа не будет компилироваться, и она создаст [ошибку компилятора C2466](../../error-messages/compiler-errors-1/compiler-error-c2466.md) , так как **длинное** значение превышает 1 байт.

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

---
title: Ключевое слово _Static_assert и макрос static_assert (C11)
description: Описывает ключевое слово _Static_assert (C11) и макрос static_assert (C11).
ms.date: 10/13/2020
f1_keywords:
- static_assert_c
- _Static_assert
helpviewer_keywords:
- assertions [C], _Static_assert, static_assert
ms.openlocfilehash: dbe49b1dcbb8dd4e0d9df678f4456bc605e01c3f
ms.sourcegitcommit: 651348f8cd92ab0d52f09e9225a7eb41562559db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92060981"
---
# <a name="_static_assert-keyword-and-static_assert-macro-c11"></a>Ключевое слово _Static_assert и макрос static_assert (C11)

Проверяет утверждение во время компиляции. Если заданное константное выражение имеет значение **`false`** , то компилятор выводит указанное сообщение и компиляция завершается с ошибкой C2338; в противном случае не имеет силы. Нововведение в стандарте C11.

Ключевое слово **`_Static_assert`** было представлено в стандарте C11.
Макрос **`static_assert`** также был представлен в стандарте C11 и сопоставляется с ключевым словом **`_Static_assert`** .

## <a name="syntax"></a>Синтаксис

```C
_Static_assert(constant-expression, string-literal);
static_assert(constant-expression, string-literal);
```

### <a name="parameters"></a>Параметры

*Константное выражение*\
Целочисленное константное выражение, которое можно полностью вычислить во время компиляции. Если выражение равно нулю (false), отображается параметр *строковый литерал* и компиляция завершается с ошибкой. Если выражение не равно нулю (true), то не имеет силы.

*Строковый литерал*\
Сообщение, которое отображается, если вычисленное *константное выражение* равно нулю (false). Сообщение должно быть создано на основе [базовой кодировки компилятора](../c-language/ascii-character-set.md). Не допускается использование [многобайтовых или расширенных символов](../c-language/multibyte-and-wide-characters.md).

## <a name="remarks"></a>Remarks

Ключевое слово **`_Static_assert`** и макрос **`static_assert`** позволяют проверить программное утверждение во время компиляции. Их можно использовать как на глобальном уровне, так и в области действия функции.

В отличие от них [макрос assert и функции _assert и _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) используются для проверки программного утверждения во время выполнения, что влечет за собой дополнительные затраты ресурсов времени выполнения.

**Поведение в системах Майкрософт**

В языке C при отсутствии `<assert.h>` компилятор Microsoft Visual C/C++ обрабатывает **`static_assert`** как ключевое слово, сопоставляемое с **`_Static_assert`** . Рекомендуется использовать **`static_assert`** , так как в этом случае один и тот же код будет работать как в C, так и в C++.

## <a name="example-of-a-compile-time-assert"></a>Пример утверждения времени компиляции

В следующем примере **`static_assert`** и **`_Static_assert`** используются для проверки количества элементов перечисления и того, имеют ли целые числа ширину 32 бит.

```C
// requires /std:c11 or higher
#include <assert.h>

enum Items
{
    A,
    B,
    C,
    LENGTH
};

int main()
{
    // _Static_assert is a C11 keyword
    _Static_assert(LENGTH == 3, "Expected Items enum to have three elements");

    // Preferred: static_assert maps to _Static_Assert and is compatible with C++
    static_assert(sizeof(int) == 4, "Expecting 32 bit integers"); 

    return 0;
}
```

## <a name="requirements"></a>Requirements (Требования)

|Макрос|Обязательный заголовок|
|-------------|---------------------|
|**`static_assert`**|\<assert.h>|

## <a name="see-also"></a>См. также раздел

[Макрос _STATIC_ASSERT](../c-runtime-library/reference/static-assert-macro.md)\
[Макрос assert и функции _assert и _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)
[/std (определение стандартной версии языка)](../build/reference/std-specify-language-standard-version.md)
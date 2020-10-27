---
title: Ключевое слово _Noreturn и макрос noreturn (C11)
description: Описывает ключевое слово `_Noreturn` и макрос `noreturn`.
ms.date: 10/19/2020
f1_keywords:
- _Noreturn_c
- noreturn
helpviewer_keywords:
- keywords [C]
ms.openlocfilehash: 68448d8b8c999c92fb240100c25048fa94a559b9
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274693"
---
# <a name="_noreturn-keyword-and-noreturn-macro-c11"></a>Ключевое слово `_Noreturn` и макрос `noreturn` (C11)

Ключевое слово `_Noreturn` было представлено в стандарте C11. Оно указывает компилятору, что функция, к которой оно применяется, не возвращается в вызывающий объект. Таким образом, компилятор знает, что код после вызова функции `_Noreturn` недостижим. Примером функции, которая не выполняет возврат, является [abort](../c-runtime-library/reference/abort.md). Если поток управления может вернуться в вызывающий объект, функция не должна иметь атрибут `_Noreturn`.

Это ключевое слово обычно используется в удобном макросе `noreturn`, который находится в файле <stdnoreturn.h> и сопоставляется с ключевым словом `_Noreturn`.

Ключевое слово `_Noreturn` (или эквивалентный ему макрос `noreturn`) позволяет четко описать предназначение функции пользователям, которые в дальнейшем будут работать с кодом, а также определить код, который по каким-либо причинам является недоступным.

Функция, помеченная `noreturn`, не должна включать тип возвращаемого значения, так как она не возвращает значение вызывающему объекту. Оно должно иметь значение `void`.

## <a name="example-using-noreturn-macro-and-_noreturn-keyword"></a>Пример использования макроса `noreturn` и ключевого слова `_Noreturn `

В следующем примере иллюстрируется использование ключевого слова `_Noreturn` и эквивалентного ему макроса `noreturn`.

Если используется макрос `noreturn`, который можно игнорировать, функция IntelliSense может возвращать ложную ошибку `E0065`. Ее появление не мешает запустить пример.

```C
// Compile with Warning Level4 (/W4) and /std:c11
#include <stdio.h>
#include <stdlib.h>
#include <stdnoreturn.h>

noreturn void fatal_error(void)
{
    exit(3);
}

_Noreturn void not_coming_back(void)
{
    puts("There's no coming back");
    fatal_error();
    return; // warning C4645 - function declared with noreturn has a return statement
}

void done(void)
{
    puts("We'll never get here");
}

int main(void)
{
    not_coming_back();
    done(); // warning c4702 - unreachable code

    return 0;
}
```

## <a name="requirements"></a>Requirements (Требования)

|Макрос|Обязательный заголовок|
|-------------|---------------------|
|**`noreturn`**|\<stdnoreturn.h>|

## <a name="see-also"></a>См. также раздел

[/std (определение стандартной версии языка)](../build/reference/std-specify-language-standard-version.md)\
[/W4 (выбор уровня предупреждения)](../build/reference/compiler-option-warning-level.md)\
[Предупреждение C4702](../error-messages\compiler-warnings\compiler-warning-level-4-c4702.md)\
[__declspec(noreturn)](../cpp/noreturn.md)

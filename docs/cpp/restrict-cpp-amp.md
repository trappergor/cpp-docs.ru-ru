---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 5a0011d11e4a59c9ca3a5e18f44d4cf831b21582
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366645"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Спецификатор ограничения может применяться к объявлениям функций и лямбда-выражений. Он реализует ограничения на код функции и на ее поведение в приложениях, в которых используется среда выполнения C++ AMP.

> [!NOTE]
> Для получения информации об **элементе ограничения** ключевого слова, которое является частью атрибутов **__declspec** класса хранения, [см.](../cpp/restrict.md)

Оговорка **об ограничении** принимает следующие формы:

|Предложение|Описание|
|------------|-----------------|
|`restrict(cpu)`|В функции могут использоваться все возможности языка C++. Вызывать ее могут только другие функции, объявленные с помощью функции restrict(cpu).|
|`restrict(amp)`|В функции может использоваться только то подмножество языка C++, выполнение которого может ускорить C++ AMP.|
|Последовательность функций `restrict(cpu)` и `restrict(amp)`.|Функция должна соблюдать ограничения, устанавливаемые обеими функциями: и `restrict(cpu)`, и `restrict(amp)`. Вызывать ее могут функции, объявленные при помощи `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` или `restrict(amp, cpu)`.<br /><br /> Форма `restrict(A) restrict(B)` может быть записана в виде `restrict(A,B)`.|

## <a name="remarks"></a>Remarks

Ключевое слово **ограничения** является контекстуальным ключевым словом. Спецификаторы ограничения `cpu` и `amp` не являются зарезервированными словами. Список спецификаторов не может быть расширен. Функция, не имеюв оговорка **об ограничении,** такая `restrict(cpu)` же, как и функция, имеюая положение.

Для функции с предложением `restrict(amp)` действуют следующие ограничения:

- Функция может вызывать только функции с предложением `restrict(amp)`.

- Функция должна поддерживать подстановку.

- Функция может декларировать только **int,** **unsigned int,** **float,** и **двойные** переменные, а также классы и структуры, которые содержат только эти типы. **bool** также допускается, но она должна быть 4-байт-выровнены, если вы используете его в составе типа.

- Лямбда-функции не могут захватывать по ссылке и не могут захватывать указатели.

- Указатели с одним косвенным обращением и ссылки поддерживаются только как локальные переменные, аргументы функций и типы возвращаемых значений.

- Следующие возможности не допускаются:

  - Рекурсия.

  - Переменные, объявленные с [нестабильным](../cpp/volatile-cpp.md) ключевым словом.

  - Виртуальные функции.

  - Указатели на функции.

  - Указатели на функции-члены.

  - Указатели в структурах.

  - Указатели на указатели.

  - **Гото** заявления.

  - Операторы с метками.

  - **попробуйте,** **поймать,** или **бросить** заявления.

  - Глобальные переменные.

  - Статические переменные. Вместо этого используйте [ключевое слово tile_static.](../cpp/tile-static-keyword.md)

  - **dynamic_cast** бросает.

  - Оператор **типидов.**

  - Объявления asm.

  - Использование vararg.

Для обсуждения ограничений функции [см.](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/)

## <a name="example"></a>Пример

В следующем примере показано, как использовать `restrict(amp)`положение.

```cpp
void functionAmp() restrict(amp) {}
void functionNonAmp() {}

void callFunctions() restrict(amp)
{
    // int is allowed.
    int x;
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.
    // long long int y;

    // Calling an amp-restricted function is allowed.
    functionAmp();

    // Calling a non-amp-restricted function is not allowed.
    // functionNonAmp();
}
```

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)

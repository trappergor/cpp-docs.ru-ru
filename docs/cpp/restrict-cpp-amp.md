---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 3609e3f0541cfd8a8af8559d8d49e6a77c00d91c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403390"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Спецификатор ограничения может применяться к объявлениям функций и лямбда-выражений. Он реализует ограничения на код функции и на ее поведение в приложениях, в которых используется среда выполнения C++ AMP.

> [!NOTE]
>  Сведения о **ограничить** ключевое слово, которое является частью **__declspec** атрибуты класса хранения, см. в разделе [ограничить](../cpp/restrict.md).

**Ограничить** предложение принимает следующие формы:

|Предложение|Описание|
|------------|-----------------|
|`restrict(cpu)`|В функции могут использоваться все возможности языка C++. Вызывать ее могут только другие функции, объявленные с помощью функции restrict(cpu).|
|`restrict(amp)`|В функции может использоваться только то подмножество языка C++, выполнение которого может ускорить C++ AMP.|
|Последовательность функций `restrict(cpu)` и `restrict(amp)`.|Функция должна соблюдать ограничения, устанавливаемые обеими функциями: и `restrict(cpu)`, и `restrict(amp)`. Вызывать ее могут функции, объявленные при помощи `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` или `restrict(amp, cpu)`.<br /><br /> Форма `restrict(A) restrict(B)` может быть записана в виде `restrict(A,B)`.|

## <a name="remarks"></a>Примечания

**Ограничить** ключевое слово является контекстным ключевым словом. Спецификаторы ограничения `cpu` и `amp` не являются зарезервированными словами. Список спецификаторов не может быть расширен. Функция, которая не имеет **ограничить** предложение является таким же, как функции, которая имеет `restrict(cpu)` предложение.

Для функции с предложением `restrict(amp)` действуют следующие ограничения:

- Функция может вызывать только функции с предложением `restrict(amp)`.

- Функция должна поддерживать подстановку.

- Функции можно объявить только **int**, **unsigned int**, **float**, и **двойные** переменные и классы и структуры, содержащие только Эти типы. **bool** также допустимы, но он должен быть 4-байтное выравнивание при использовании в составном типе.

- Лямбда-функции не могут захватывать по ссылке и не могут захватывать указатели.

- Указатели с одним косвенным обращением и ссылки поддерживаются только как локальные переменные, аргументы функций и типы возвращаемых значений.

- Следующие возможности не допускаются:

   - Рекурсия.

   - Переменные, объявленные с [volatile](../cpp/volatile-cpp.md) ключевое слово.

   - Виртуальные функции.

   - Указатели на функции.

   - Указатели на функции-члены.

   - Указатели в структурах.

   - Указатели на указатели.

   - **GoTo** инструкций.

   - Операторы с метками.

   - **Попробуйте**, **catch**, или **throw** инструкций.

   - Глобальные переменные.

   - Статические переменные. Используйте [ключевое слово tile_static](../cpp/tile-static-keyword.md) вместо этого.

   - **dynamic_cast** приведения.

   - **Typeid** оператор.

   - Объявления asm.

   - Использование vararg.

Описание ограничения функций, см. в разделе [ограничить ограничения (amp)](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/).

## <a name="example"></a>Пример

В следующем примере показано, как использовать `restrict(amp)`предложение.

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

## <a name="see-also"></a>См. также

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)
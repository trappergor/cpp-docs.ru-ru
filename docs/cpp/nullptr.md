---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 51df20ea00e5dd77ab1fc1a2a01253b8f788ad0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358851"
---
# <a name="nullptr"></a>nullptr

Обозначает константу-указатель NULL типа `std::nullptr_t`, которая может быть преобразована к любому типу необработанного указателя.  Хотя вы можете использовать ключевое слово **nullptr** без включения каких-либо заголовков, если ваш код использует тип, `std::nullptr_t`то вы должны определить его, включив заголовок. `<cstddef>`

> [!NOTE]
> Ключевое слово **nullptr** также определяется в си/CLI для управляемых код-приложений и не является взаимозаменяемым с ключевым словом ISO Standard C. Если ваш код может быть скомпилирован с помощью опции компилятора [/clr,](../build/reference/clr-common-language-runtime-compilation.md) которая нацелена на управляемый код, затем используйте `__nullptr` в любой строке кода, где вы должны гарантировать, что компилятор использует родную интерпретацию C'. Для получения дополнительной информации [см.](../extensions/nullptr-cpp-component-extensions.md)

## <a name="remarks"></a>Remarks

Избегайте использования NULL`0`или нуля () в качестве константы нулевой указатель; **nullptr** менее уязвим для неправильного использования и работает лучше в большинстве ситуаций.  Например, если для функции `func(std::pair<const char *, double>)` произвести вызов `func(std::make_pair(NULL, 3.14))`, возникнет ошибка компилятора.  Макрос NULL разворачивается в `0`, поэтому вызов `std::make_pair(0, 3.14)` возвращает значение `std::pair<int, double>`, которое невозможно преобразовать к типу параметра `std::pair<const char *, double>` функции func().  Вызов `func(std::make_pair(nullptr, 3.14))` успешно компилируется, поскольку `std::make_pair(nullptr, 3.14)` возвращает значение `std::pair<std::nullptr_t, double>`, которое допускает преобразование в тип `std::pair<const char *, double>`.

## <a name="see-also"></a>См. также раздел

[Keywords](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(КЗ/CLI)

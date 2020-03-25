---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 223f4c3e8c838698f9716e241543db405c9394af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177772"
---
# <a name="nullptr"></a>nullptr

Обозначает константу-указатель NULL типа `std::nullptr_t`, которая может быть преобразована к любому типу необработанного указателя.  Хотя можно использовать ключевое слово **nullptr** без включения заголовков, если код использует тип `std::nullptr_t`, необходимо определить его, включив `<cstddef>`заголовка.

> [!NOTE]
>  Ключевое слово **nullptr** также определяется в C++/CLI для приложений с управляемым кодом и не является взаимозаменяемым с ключевым C++ словом Standard ISO. Если код может быть скомпилирован с помощью параметра компилятора [/CLR](../build/reference/clr-common-language-runtime-compilation.md) , который предназначен для управляемого кода, используйте `__nullptr` в любой строке кода, где необходимо гарантировать, что компилятор использует интерпретацию в машинном C++ коде. Дополнительные сведения см. в разделе [nullptr](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Remarks

Старайтесь не использовать NULL или нуль (`0`) как константу указателя NULL; **nullptr** менее уязвим к неправильному использовании и работает лучше в большинстве случаев.  Например, если для функции `func(std::pair<const char *, double>)` произвести вызов `func(std::make_pair(NULL, 3.14))`, возникнет ошибка компилятора.  Макрос NULL разворачивается в `0`, поэтому вызов `std::make_pair(0, 3.14)` возвращает значение `std::pair<int, double>`, которое невозможно преобразовать к типу параметра `std::pair<const char *, double>` функции func().  Вызов `func(std::make_pair(nullptr, 3.14))` успешно компилируется, поскольку `std::make_pair(nullptr, 3.14)` возвращает значение `std::pair<std::nullptr_t, double>`, которое допускает преобразование в тип `std::pair<const char *, double>`.

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[nullptr](../extensions/nullptr-cpp-component-extensions.md)(C++/CLI)

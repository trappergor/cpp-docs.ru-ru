---
title: Контейнеры (современный C++)
ms.date: 01/18/2018
ms.topic: conceptual
ms.openlocfilehash: 37b540132fc9ddc03d5eaafd33c545b5db5e7935
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926256"
---
# <a name="containers-modern-c"></a>Контейнеры (современный C++)

По умолчанию используйте [vector](../standard-library/vector-class.md) в качестве предпочтительного последовательного контейнера в C++. Это эквивалентно `List<T>` языку .NET.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Используйте [Map](../standard-library/map-class.md) (не `unordered_map`) в качестве ассоциативного контейнера по умолчанию. Используйте [Set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md)и [мультинабор](../standard-library/multiset-class.md) для создания & нескольких вариантов.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

При необходимости оптимизации производительности рассмотрите возможность использования следующих средств:

- Тип [массива](../standard-library/array-class-stl.md) при внедрении важен, например, как член класса.

- Неупорядоченные ассоциативные контейнеры, такие как [unordered_map](../standard-library/unordered-map-class.md). Они имеют меньшие издержки на элементы и уточняющие запросы во время поиска, но могут быть труднее и эффективно использовать их.

- Отсортировано `vector`. Дополнительные сведения см. в разделе [Алгоритмы](../cpp/algorithms-modern-cpp.md).

Не используйте массивы в стиле языка C. Для более старых API, которым требуется прямой доступ к данным, используйте методы доступа, `f(vec.data(), vec.size());` такие как.

Дополнительные сведения о контейнерах см. в разделе [ C++ стандартные библиотечные контейнеры](../standard-library/stl-containers.md).

## <a name="see-also"></a>См. также

[Возвращение к C++ (современный C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)

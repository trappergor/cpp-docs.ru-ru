---
title: Контейнеры (современный C++) | Документы Microsoft
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49a77234b679fd61d801bb78d751891467d6b4e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="containers-modern-c"></a>Контейнеры (современный C++)

По умолчанию используют [вектор](../standard-library/vector-class.md) как предпочтительный последовательного контейнера в C++. Это эквивалентно `List<T>` в языках .NET.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

Используйте [карты](../standard-library/map-class.md) (не `unordered_map`) в качестве ассоциативного контейнера по умолчанию. Используйте [задать](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), и [мультинабор](../standard-library/multiset-class.md) для вырожденного & нескольких случаях.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

При необходимости для оптимизации производительности, рассмотрите возможность использования:

- [Массива](../standard-library/array-class-stl.md) типов при внедрении важна, например, как член класса.

- Неупорядоченные ассоциативные контейнеры, такие как [unordered_map](../standard-library/unordered-map-class.md). Они должны нижнему элементу издержки и постоянным по времени поиском, но они могут быть труднее использовать правильную и эффективную.

- Сортировка **вектор**. Дополнительные сведения см. в разделе [Алгоритмы](../cpp/algorithms-modern-cpp.md).

Не используйте массивы в стиле C. Для старых API, которые требуется прямой доступ к данным, используйте методы доступа, например `f(vec.data(), vec.size());` вместо него.

Дополнительные сведения о контейнерах см. в разделе [контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)  
[Справочник по языку C++](../cpp/cpp-language-reference.md)  
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)  

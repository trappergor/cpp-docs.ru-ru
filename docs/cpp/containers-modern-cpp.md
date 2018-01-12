---
title: "Контейнеры (современный C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffad61c015c38d808b35ebffd98f74733d0997de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
1.  [Массива](../standard-library/array-class-stl.md) типов при внедрении важна, например, как член класса.  
  
2.  Неупорядоченные ассоциативные контейнеры, такие как [unordered_map] ((.. /Standard-Library/Unordered-MAP-Class.MD). Они должны нижнему элементу издержки и постоянным по времени поиском, но они могут быть труднее использовать правильную и эффективную.  
  
3.  Сортировка `vector`. Дополнительные сведения см. в разделе [Алгоритмы](../cpp/algorithms-modern-cpp.md).  
  
Не используйте массивы в стиле C. Для старых API, которые требуется прямой доступ к данным, используйте методы доступа, например `f(vec.data(), vec.size());` вместо него.  
  
Дополнительные сведения о контейнерах см. в разделе [контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).  
  
## <a name="see-also"></a>См. также  
 [Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)

---
title: '&lt;размещать&gt;'
ms.date: 05/28/2020
f1_keywords:
- <span>
helpviewer_keywords:
- span header
ms.openlocfilehash: 7d21023c90472e5c2e1b28d9fa85e517da4a21ae
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846190"
---
# <a name="ltspangt"></a>&lt;размещать&gt;

`span`Представляет собой представление для непрерывной последовательности объектов. Он обеспечивает быстрый и ограниченный доступ. В отличие от `vector` или `array` , он не "владеет" элементами, к которым он предоставляет доступ.

Подробные сведения см. в разделе [класс span](span-class.md) . Ниже приведен пример того, как можно использовать диапазон.

```cpp
#include <span>
#include <iostream>

void Show(std::span<int> someValues)
{
    // show values in reverse
    for (auto rIt = someValues.rbegin(); rIt != someValues.rend(); ++rIt)
    {
        std::cout << *rIt;
    }

    // show a subspan
    for (auto& i : someValues.subspan(1, 2))
    {
        std::cout << i;
    }
}

int main()
{
    int numbers[]{ 0,1,2,3,4 };
    Show(numbers); // note conversion from array to span
}
```

## <a name="requirements"></a>Требования

**Заголовок:**\<span>

**Пространство имен:** std

**Параметр компилятора:** /std: c + + Latest

## <a name="members"></a>Элементы

### <a name="classes"></a>Классы

|name|Описание|
|-|:-|
|[размещать](span-class.md)| Предоставляет представление для непрерывной последовательности объектов. |

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|:-|
|[Оператор =](span-class.md#op_eq)| Назначение диапазона |
|[станции\[\]](span-class.md#op_at)| Доступ к элементам |

### <a name="functions"></a>Функции

|Имя|Описание|
|-|:-|
| [as_bytes](span-functions.md#as_bytes)| Возвращает базовые байты, которые доступны только для чтения. |
| [as_writable_bytes](span-functions.md#as_writable_bytes) | Получение базовых байтов диапазона. |

### <a name="constants"></a>Константы

|Имя|Описание|
|-|:-|
| **dynamic_extent** | Указывает, что размер диапазона определяется во время выполнения, а не во времени компиляции. Когда число элементов в диапазоне известно во время компиляции, оно указывается в качестве `Extent` параметра шаблона. Если число неизвестно до времени выполнения, укажите `dynamic_extent` вместо него. |

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)

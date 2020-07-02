---
title: '&lt;размещать&gt;'
ms.date: 05/28/2020
f1_keywords:
- <span>
helpviewer_keywords:
- span header
ms.openlocfilehash: 27f27acfa84a3ccc42586593747e4657146cbe39
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813539"
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

|||
|-|:-|
|[размещать](span-class.md)| Предоставляет представление для непрерывной последовательности объектов. |

### <a name="operators"></a>Операторы

|||
|-|:-|
|[Оператор =](span-class.md#op_eq)| Назначение диапазона |
|[станции\[\]](span-class.md#op_at)| Доступ к элементам |

### <a name="functions"></a>Функции

|||
|-|:-|
| [as_bytes](span-functions.md#as_bytes)| Возвращает базовые байты, которые доступны только для чтения. |
| [as_writable_bytes](span-functions.md#as_writable_bytes) | Получение базовых байтов диапазона. |

### <a name="constants"></a>Константы

|||
|-|:-|
| **dynamic_extent** | Указывает, что размер диапазона определяется во время выполнения, а не во времени компиляции. Когда число элементов в диапазоне известно во время компиляции, оно указывается в качестве `Extent` параметра шаблона. Если число неизвестно до времени выполнения, укажите `dynamic_extent` вместо него. |

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)

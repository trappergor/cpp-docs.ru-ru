---
title: Структура char_traits&lt;wchar_t&gt;
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: a2f8a882020ddb3d87436d08b3d85ea9407b1c08
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458967"
---
# <a name="chartraitsltwchartgt-struct"></a>Структура char_traits&lt;wchar_t&gt;

Класс, являющийся специализацией структуры шаблона **char_traits\<CharType >** к элементу типа **wchar_t**.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества библиотечных функций, которые управляют объектами этого типа **wchar_t**.

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура char_traits](../standard-library/char-traits-struct.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

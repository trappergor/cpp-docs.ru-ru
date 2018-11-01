---
title: Структура char_traits&lt;wchar_t&gt;
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: ef40a34b5aa874c8bdf48aeb7657ae3496160eec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584747"
---
# <a name="chartraitsltwchartgt-struct"></a>Структура char_traits&lt;wchar_t&gt;

Класс, который является специализацией структуры шаблона **char_traits\<CharType >** на элемент типа **wchar_t**.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества библиотечных функций, манипулирующих объектами данного типа **wchar_t**.

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура char_traits](../standard-library/char-traits-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

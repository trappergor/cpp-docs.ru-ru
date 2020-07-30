---
title: Определения типов &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: a61eeb98dfd275b10749e86043a3f7042be84ab9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224660"
---
# <a name="ltostreamgt-typedefs"></a>Определения типов &lt;ostream&gt;

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a><a name="ostream"></a>ostream

Создает тип из basic_ostream, который специализируется на **`char`** и `char_traits` специализируется на **`char`** .

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_ostream](../standard-library/basic-ostream-class.md)шаблона класса, специализированного для элементов типа **`char`** с признаками символа по умолчанию.

## <a name="wostream"></a><a name="wostream"></a>wostream

Создает тип из basic_ostream, который специализируется на **`wchar_t`** и `char_traits` специализируется на **`wchar_t`** .

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_ostream](../standard-library/basic-ostream-class.md)шаблона класса, специализированного для элементов типа **`wchar_t`** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<ostream>](../standard-library/ostream.md)

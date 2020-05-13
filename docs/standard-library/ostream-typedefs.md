---
title: Определения типов &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 82539a3fdadf10d340ca957756e235e8ae00b267
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373582"
---
# <a name="ltostreamgt-typedefs"></a>Определения типов &lt;ostream&gt;

|||
|-|-|
|[Ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a><a name="ostream"></a>Ostream

Создает тип из basic_ostream, который `char_traits` специализируется на **char** и специализируется на **char**.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ostream,](../standard-library/basic-ostream-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="wostream"></a><a name="wostream"></a>wostream

Создает тип из basic_ostream, **wchar_t** который `char_traits` специализируется на wchar_t и специализируется на **wchar_t.**

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ostream,](../standard-library/basic-ostream-class.md)специализировавшегося на элементах **wchar_t** типа с чертами символов по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<ostream>](../standard-library/ostream.md)

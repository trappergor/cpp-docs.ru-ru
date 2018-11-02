---
title: Определения типов &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 02936fdfc990ea65a99b2875cf7f482eb2ce4ebe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429748"
---
# <a name="ltostreamgt-typedefs"></a>Определения типов &lt;ostream&gt;

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Создает тип из basic_ostream, специализированного на **char** и `char_traits` специализированный на **char**.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="wostream"></a>  wostream

Создает тип из basic_ostream, специализированного на **wchar_t** и `char_traits` специализированный на **wchar_t**.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Примечания

Тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)<br/>

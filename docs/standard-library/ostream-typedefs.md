---
title: Определения типов &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 18f30a12a6f4d2b97cb5dca3ace98e6241d856a7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447164"
---
# <a name="ltostreamgt-typedefs"></a>Определения типов &lt;ostream&gt;

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Создает тип из basic_ostream, специализированного для типа **char** и `char_traits` специализированного для типа **char**.

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="wostream"></a>  wostream

Создает тип из basic_ostream, специализированного для **wchar_t** и `char_traits` специализированного для **wchar_t**.

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом класса шаблона [basic_ostream](../standard-library/basic-ostream-class.md), специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)

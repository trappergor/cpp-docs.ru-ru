---
title: Определения типов &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 9a25e4aa9ee42ea36d1bb8d6b196b36ff5c97758
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856599"
---
# <a name="ltistreamgt-typedefs"></a>Определения типов &lt;istream&gt;

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Тип, `basic_iostream` специализированный для **char**.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_iostream](../standard-library/basic-iostream-class.md)шаблона класса, специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="istream"></a>  istream

Тип, `basic_istream` специализированный для **char**.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_istream](../standard-library/basic-istream-class.md)шаблона класса, специализированного для элементов типа **char** с признаками символа по умолчанию.

## <a name="wiostream"></a>  wiostream

Тип, `basic_iostream` специализированный для **wchar_t**.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_iostream](../standard-library/basic-iostream-class.md)шаблона класса, специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="wistream"></a>  wistream

Тип, `basic_istream` специализированный для **wchar_t**.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_istream](../standard-library/basic-istream-class.md)шаблона класса, специализированного для элементов типа **wchar_t** с признаками символа по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<istream>](../standard-library/istream.md)

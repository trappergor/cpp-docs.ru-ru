---
title: Определения типов &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: e9228bddcc3b99503b6b5f0e93b5ed6eeed773d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363085"
---
# <a name="ltistreamgt-typedefs"></a>Определения типов &lt;istream&gt;

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a><a name="iostream"></a>Iostream

Тип, `basic_iostream` специализирующийся на **char**.

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_iostream,](../standard-library/basic-iostream-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="istream"></a><a name="istream"></a>Istream

Тип, `basic_istream` специализирующийся на **char**.

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_istream,](../standard-library/basic-istream-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="wiostream"></a><a name="wiostream"></a>wiostream

Тип, `basic_iostream` специализирующийся на **wchar_t**.

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_iostream,](../standard-library/basic-iostream-class.md)специализировавшегося на элементах типа **wchar_t** с чертами характера по умолчанию.

## <a name="wistream"></a><a name="wistream"></a>wistream

Тип, `basic_istream` специализирующийся на **wchar_t**.

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_istream,](../standard-library/basic-istream-class.md)специализировавшегося на элементах типа **wchar_t** с чертами символов по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<istream>](../standard-library/istream.md)

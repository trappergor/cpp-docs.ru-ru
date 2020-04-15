---
title: Определения типов &lt;streambuf&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 8eb058f161a9f30ccf5e9d49307b50c215f79c22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376682"
---
# <a name="ltstreambufgt-typedefs"></a>Определения типов &lt;streambuf&gt;

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>Streambuf

Специализация, `basic_streambuf` которая использует **символ** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_streambuf,](../standard-library/basic-streambuf-class.md)специализировавшегося на элементах **символа** типа с чертами символов по умолчанию.

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf

Специализация, `basic_streambuf` которая использует **wchar_t** в качестве параметров шаблона.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_streambuf,](../standard-library/basic-streambuf-class.md)специализировавшегося на элементах типа **wchar_t** с чертами символов по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<стри>мбуф](../standard-library/streambuf.md)

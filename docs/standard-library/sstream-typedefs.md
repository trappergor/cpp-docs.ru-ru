---
title: Определения типов &lt;sstream&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::istringstream
- iosfwd/std::ostringstream
- iosfwd/std::stringbuf
- iosfwd/std::stringstream
- iosfwd/std::wistringstream
- iosfwd/std::wostringstream
- iosfwd/std::wstringbuf
- iosfwd/std::wstringstream
ms.assetid: d102edd2-ecea-4a35-a398-cf96e58dd422
ms.openlocfilehash: c25d3fa66b5105ad2e1ff5a08ebdde90d1d156be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336636"
---
# <a name="ltsstreamgt-typedefs"></a>Определения типов &lt;sstream&gt;

||||
|-|-|-|
|[istringstream](#istringstream)|[ostringstream](#ostringstream)|[stringbuf](#stringbuf)|
|[stringstream](#stringstream)|[wistringstream](#wistringstream)|[wostringstream](#wostringstream)|
|[wstringbuf](#wstringbuf)|[wstringstream](#wstringstream)|

## <a name="istringstream"></a><a name="istringstream"></a>istringstream

Создает тип, `basic_istringstream` специализирующийся на параметре шаблона **char.**

```cpp
typedef basic_istringstream<char> istringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_istringstream,](../standard-library/basic-istringstream-class.md)специализируемого на элементах типа **char.**

## <a name="ostringstream"></a><a name="ostringstream"></a>ostringstream

Создает тип, `basic_ostringstream` специализирующийся на параметре шаблона **char.**

```cpp
typedef basic_ostringstream<char> ostringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ostringstream,](../standard-library/basic-ostringstream-class.md)специализируемого на элементах **символа**типа.

## <a name="stringbuf"></a><a name="stringbuf"></a>stringbuf

Создает тип, `basic_stringbuf` специализирующийся на параметре шаблона **char.**

```cpp
typedef basic_stringbuf<char> stringbuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_stringbuf,](../standard-library/basic-stringbuf-class.md)специализируемого на элементах **символа**типа.

## <a name="stringstream"></a><a name="stringstream"></a>струнный поток

Создает тип, `basic_stringstream` специализирующийся на параметре шаблона **char.**

```cpp
typedef basic_stringstream<char> stringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_stringstream,](../standard-library/basic-stringstream-class.md)специализируемого на элементах типа **char.**

## <a name="wistringstream"></a><a name="wistringstream"></a>wistringstream

Создает тип, `basic_istringstream` специализирующийся на параметре **шаблона wchar_t.**

```cpp
typedef basic_istringstream<wchar_t> wistringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_istringstream](../standard-library/basic-istringstream-class.md)шаблона класса, специализируемого на элементах **типа wchar_t.**

## <a name="wostringstream"></a><a name="wostringstream"></a>wostringstream

Создает тип, `basic_ostringstream` специализирующийся на параметре **шаблона wchar_t.**

```cpp
typedef basic_ostringstream<wchar_t> wostringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ostringstream,](../standard-library/basic-ostringstream-class.md)специализируемого на элементах типа **wchar_t.**

## <a name="wstringbuf"></a><a name="wstringbuf"></a>wstringbuf

Создает тип, `basic_stringbuf` специализирующийся на параметре **шаблона wchar_t.**

```cpp
typedef basic_stringbuf<wchar_t> wstringbuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_stringbuf](../standard-library/basic-stringbuf-class.md)шаблона класса, специализировавшегося на элементах типа **wchar_t.**

## <a name="wstringstream"></a><a name="wstringstream"></a>wstringstream

Создает тип, `basic_stringstream` специализирующийся на параметре **шаблона wchar_t.**

```cpp
typedef basic_stringstream<wchar_t> wstringstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [basic_stringstream](../standard-library/basic-stringstream-class.md)шаблона класса, специализируемого на элементах **wchar_t**типа.

## <a name="see-also"></a>См. также раздел

[\<sstream>](../standard-library/sstream.md)

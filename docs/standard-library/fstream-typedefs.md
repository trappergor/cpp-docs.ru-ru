---
title: Определения типов &lt;fstream&gt;
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: 57e481c131a6e4a1111b1ed88217b891d6fc96a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317196"
---
# <a name="ltfstreamgt-typedefs"></a>Определения типов &lt;fstream&gt;

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[Ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a><a name="filebuf"></a>filebuf

Тип, `basic_filebuf` специализирующийся на параметрах **шаблона char.**

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_filebuf,](../standard-library/basic-filebuf-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="fstream"></a><a name="fstream"></a>fstream

Тип, `basic_fstream` специализирующийся на параметрах **шаблона char.**

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_fstream,](../standard-library/basic-fstream-class.md)специализировавшегося на элементах **символа** типа с чертами символов по умолчанию.

## <a name="ifstream"></a><a name="ifstream"></a>Ifstream

Определяет поток, который используется для последовательного чтения однобайтовых символов из файла. `ifstream`— это typedef, который `basic_ifstream` специализируется на шаблоне класса для **char**.

Существует также `wifstream`, typedef, `basic_ifstream` который специализируется на чтении **wchar_t** двойных символов. Дополнительные сведения см. в описании [wifstream](../standard-library/fstream-typedefs.md#wifstream).

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ifstream,](../standard-library/basic-ifstream-class.md)специализировавшегося на элементах символа типа с чертами символов по умолчанию. Пример:

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a>Ofstream

Тип, `basic_ofstream` специализирующийся на параметрах **шаблона char.**

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ofstream,](../standard-library/basic-ofstream-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="wfstream"></a><a name="wfstream"></a>wfstream

Тип, `basic_fstream` специализирующийся на **параметрах шаблона wchar_t.**

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_fstream,](../standard-library/basic-fstream-class.md)специализировавшегося на элементах типа **wchar_t** с чертами символов по умолчанию.

## <a name="wifstream"></a><a name="wifstream"></a>wifstream

Тип, `basic_ifstream` специализирующийся на **параметрах шаблона wchar_t.**

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ifstream,](../standard-library/basic-ifstream-class.md)специализировавшегося на элементах **wchar_t** типа с чертами символов по умолчанию.

## <a name="wofstream"></a><a name="wofstream"></a>wofstream

Тип, `basic_ofstream` специализирующийся на **параметрах шаблона wchar_t.**

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ofstream,](../standard-library/basic-ofstream-class.md)специализировавшегося на элементах типа **wchar_t** с чертами характера по умолчанию.

## <a name="wfilebuf"></a><a name="wfilebuf"></a>wfilebuf

Тип, `basic_filebuf` специализирующийся на **параметрах шаблона wchar_t.**

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_filebuf,](../standard-library/basic-filebuf-class.md)специализировавшегося на элементах **wchar_t** типа с чертами символов по умолчанию.

## <a name="see-also"></a>См. также раздел

[\<>fstream](../standard-library/fstream.md)

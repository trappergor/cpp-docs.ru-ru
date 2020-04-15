---
title: Определения типов &lt;ios&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
ms.openlocfilehash: 0f63f65fb4c10fbe2ad538852222e6468b9061d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375405"
---
# <a name="ltiosgt-typedefs"></a>Определения типов &lt;ios&gt;

## <a name="ios"></a><a name="ios"></a>Ios

Поддерживает класс ios из старой библиотеки iostream.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ios,](../standard-library/basic-ios-class.md)специализируемого на элементах **символа** типа с чертами символов по умолчанию.

## <a name="streamoff"></a><a name="streamoff"></a>стрим-офф

Поддерживает внутренние операции.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Remarks

Тип — целое число со знаком, описывающее объект, который может хранить смещение в байтах, участвующее в различных операциях размещения потока. Его представление имеет по крайней мере 32 бита значения. Оно не обязательно достаточно велико для представления произвольных позиций внутри потока. Значение `streamoff(-1)` обычно указывает на ошибочное смещение.

## <a name="streampos"></a><a name="streampos"></a>streampos

Содержит текущее положение указателя буфера или указателя файла.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [fpos](../standard-library/fpos-class.md) <  `mbstate_t`>.

### <a name="example"></a>Пример

```cpp
// ios_streampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ofstream x( "iostream.txt" );
   x << "testing";
   streampos y = x.tellp( );
   cout << y << endl;
}
```

```Output
7
```

## <a name="streamsize"></a><a name="streamsize"></a>потокового

Указывает размер потока.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Remarks

Тип — целое число со знаком, описывающее объект, который может хранить количество элементов, участвующих в различных операциях размещения потока. Его представление имеет по крайней мере 16 битов значения. Оно не обязательно достаточно велико для представления произвольных позиций внутри потока.

### <a name="example"></a>Пример

После компиляции и запуска следующей программы рассмотрим файл Test.txt, чтобы увидеть влияние параметра `streamsize`.

```cpp
// ios_streamsize.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   char a[16] = "any such text";
   ofstream x( "test.txt" );
   streamsize y = 6;
   x.write( a, y );
}
```

## <a name="wios"></a><a name="wios"></a>wios

Поддерживает класс wios из старой библиотеки iostream.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Remarks

Тип является синонимом шаблона класса [basic_ios,](../standard-library/basic-ios-class.md)специализировавшегося на элементах типа **wchar_t** с чертами характера по умолчанию.

## <a name="wstreampos"></a><a name="wstreampos"></a>wstreampos

Содержит текущее положение указателя буфера или указателя файла.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Remarks

Тип является синонимом [fpos](../standard-library/fpos-class.md) <  `mbstate_t`>.

### <a name="example"></a>Пример

```cpp
// ios_wstreampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   wofstream xw( "wiostream.txt" );
   xw << L"testing";
   wstreampos y = xw.tellp( );
   cout << y << endl;
}
```

```Output
7
```

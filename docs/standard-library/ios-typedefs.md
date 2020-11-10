---
title: Определения типов `<ios>`
description: Описывает определения типов библиотеки стандартных шаблонов C++ (STL) `<ios>` , которые поддерживают `ios` класс из старой `iostream` библиотеки.
ms.date: 11/06/2020
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.openlocfilehash: b9dbed64c88a00f5ca065e23c4af2f3922634ece
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441272"
---
# <a name="ios-typedefs"></a>Определения типов `<ios>`

## `ios`

Поддерживает `ios` класс из старой `iostream` библиотеки.

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для шаблона класса [`basic_ios`](../standard-library/basic-ios-class.md) , специализированного для элементов типа **`char`** с признаками символа по умолчанию.

## `streamoff`

Поддерживает внутренние операции.

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>Комментарии

Тип является целым числом со знаком. Он описывает объект, который может хранить смещение в байтах в операциях позиционирования потока. Его представление имеет по крайней мере 32 бита значения. Он не обязательно достаточно велик, чтобы представлять произвольную байтовую точку в потоке. Значение `streamoff(-1)` обычно указывает на ошибочное смещение.

## `streampos`

Содержит текущее положение указателя буфера или указателя файла.

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>Комментарии

Тип является синонимом для [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t`>.

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
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```

## `streamsize`

Указывает размер потока.

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>Комментарии

Тип — целое число со знаком, описывающее объект, который может хранить количество элементов, участвующих в различных операциях размещения потока. Его представление имеет по крайней мере 16 битов значения. Он не обязательно достаточно велик, чтобы представлять произвольную байтовую точку в потоке.

### <a name="example"></a>Пример

После компиляции и запуска следующей программы Взгляните на файл, `test.txt` чтобы увидеть результат настройки `streamsize` .

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

## `wios`

Поддерживает `wios` класс из старой `iostream` библиотеки.

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>Комментарии

Этот тип является синонимом для шаблона класса [`basic_ios`](../standard-library/basic-ios-class.md) , специализированного для элементов типа **`wchar_t`** с признаками символа по умолчанию.

## `wstreampos`

Содержит текущее положение указателя буфера или указателя файла.

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>Комментарии

Тип является синонимом для [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t`>.

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
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```

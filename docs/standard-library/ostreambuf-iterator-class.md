---
title: Класс ostreambuf_iterator
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
ms.openlocfilehash: be4421a7646756da5687ebc9b98f18daf4845809
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687217"
---
# <a name="ostreambuf_iterator-class"></a>Класс ostreambuf_iterator

Шаблон класса ostreambuf_iterator описывает объект итератора вывода, который записывает последовательные элементы символов в выходной поток с помощью **оператора извлечения > >** . `ostreambuf_iterator` отличаются от таковых [класса ostream_iterator](../standard-library/ostream-iterator-class.md) тем, что используют символы вместо универсального типа для типа объекта, вставляемого в поток вывода.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>Параметры

*CharType* \
Тип, представляющий тип символа для ostreambuf_iterator. Этот аргумент является необязательным, и значение по умолчанию — **char**.

*Признаки* \
Тип, представляющий тип символа для ostreambuf_iterator. Этот аргумент является необязательным, значение по умолчанию — `char_traits`\< *CharType>.*

## <a name="remarks"></a>Заметки

Класс ostreambuf_iterator должен удовлетворять требованиям для итератора вывода. Алгоритмы можно записывать непосредственно в потоки вывода с помощью `ostreambuf_iterator`. Данный класс предоставляет итератор потока низкого уровня, обеспечивающий доступ к необработанному (неотформатированному) потоку ввода-вывода в форме символов, а также возможность обхода буферизации и преобразования символов, связанных с итераторами потоков высокого уровня.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Создает итератор `ostreambuf_iterator`, инициализированный для записи символов в поток вывода.|

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, обеспечивающий тип символа для `ostreambuf_iterator`.|
|[ostream_type](#ostreambuf_iterator_ostream_type)|Тип, обеспечивающий тип потока для `ostream_iterator`.|
|[streambuf_type](#streambuf_type)|Тип, обеспечивающий тип потока для `ostreambuf_iterator`.|
|[traits_type](#traits_type)|Тип, обеспечивающий тип признаков символа для `ostream_iterator`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[failed](#failed)|Проверяет наличие ошибок вставки в буфер потока вывода.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[operator*](#op_star)|Оператор разыменования, используемый для реализации выражения итератора вывода \* `i`  =  `x`.|
|[оператор++](#op_add_add)|Нефункциональный оператор инкремента, возвращающий `ostreambuf_iterator`, обращающийся к тому же объекту, к которому он обращался до вызова операции.|
|[оператор=](#op_eq)|Данный оператор вставляет символ в соответствующий буфер потока.|

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="char_type"></a>  ostreambuf_iterator::char_type

Тип, обеспечивающий тип символа для `ostreambuf_iterator`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Заметки

Этот тип является синонимом для параметра шаблона `CharType`.

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="failed"></a>  ostreambuf_iterator::failed

Проверяет наличие ошибок вставки в буфер потока вывода.

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

**true**, если ранее вставка в буфер потока вывода закончилась неудачно; в противном случае **false**.

### <a name="remarks"></a>Заметки

Функция-член возвращает **true**, если в любом предыдущем использовании члена `operator=` вызов **subf**_-> `sputc` вернул **eof**.

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_failed.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'a';
   charOut ++;
*charOut  = 'b';
   charOut ++;
*charOut = 'c';
   cout << " are characters output individually." << endl;

   bool b1 = charOut.failed ( );
   if (b1)
       cout << "At least one insertion failed." << endl;
   else
       cout << "No insertions failed." << endl;
}
/* Output:
abc are characters output individually.
No insertions failed.
*/
```

## <a name="op_star"></a>ostreambuf_iterator:: operator \*

Нефункциональный оператор разыменования, используемый для реализации выражения итератора вывода \* *i* = *x*.

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>Возвращаемое значение

Объект-итератор ostreambuf.

### <a name="remarks"></a>Заметки

Этот оператор работает только в выражении итератора вывода \* *i* = *x* для вывода символов в буфер потока. Применяется к итератору ostreambuf. Он возвращает итератор; **\*iter** возвращает **iter**,

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;   // no effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="op_add_add"></a>  ostreambuf_iterator::operator++

Нефункциональный оператор приращения, который возвращает итератор ostream, обращающийся к тому же символу, к которому он обращался до вызова операции.

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на изначально адресованный символ или на определенный в реализации объект, который можно преобразовать в `ostreambuf_iterator`\< **CharType**, **Traits**>.

### <a name="remarks"></a>Заметки

Оператор используется для реализации выражения итератора вывода \* *i* = *x*.

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="op_eq"></a>  ostreambuf_iterator::operator=

Данный оператор вставляет символ в соответствующий буфер потока.

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>Параметры

*_Char* \
Символ для вставки в буфер потока.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на символ, вставленный в буфер потока.

### <a name="remarks"></a>Заметки

Оператор присваивания, используемый для реализации выражения итератора вывода \* *i* = *x* для записи в поток вывода.

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   // with new line delimiter
   ostreambuf_iterator<char> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
*charOutBuf = 'O';
   charOutBuf++;      // No effect on iterator position
*charOutBuf = 'U';
*charOutBuf = 'T';
}
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator

Создает итератор `ostreambuf_iterator`, инициализированный для записи символов в поток вывода.

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>Параметры

*strbuf* \
Выходной объект streambuf, используемый для инициализации указателя буфера потока вывода.

*Ostr* \
Выходной объект stream, используемый для инициализации указателя буфера потока вывода.

### <a name="remarks"></a>Заметки

Первый конструктор инициализирует указатель буфера потока вывода с *strBuf*.

Второй конструктор инициализирует указатель буфера потока вывода значением `Ostr`. `rdbuf` Сохраненный указатель не должен быть пустым указателем (NULL).

### <a name="example"></a>Пример

```cpp
// ostreambuf_iteratorOstreambuf_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostreambuf_iterator for stream cout
   ostreambuf_iterator<char> charOut ( cout );

*charOut = 'O';
   charOut ++;
*charOut  = 'U';
   charOut ++;
*charOut = 'T';
   cout << " are characters output individually." << endl;

   ostreambuf_iterator<char> strOut ( cout );
   string str = "These characters are being written to the output stream.\n ";
   copy ( str.begin ( ), str. end ( ), strOut );
}
/* Output:
OUT are characters output individually.
These characters are being written to the output stream.
*/
```

## <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type

Тип, обеспечивающий тип потока для `ostream_iterator`.

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Заметки

Тип является синонимом для `basicOstream`\< **CharType**, **Traits**>

### <a name="example"></a>Пример

См. раздел [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) с примером объявления и использования `ostream_type`.

## <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type

Тип, обеспечивающий тип потока для `ostreambuf_iterator`.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Заметки

Этот тип является синонимом для `basic_streambuf` \< **CharType**, признаков >, класса потока для буферов ввода- **вывода, которые**становятся `streambuf`, когда специализированная для символьного типа **char**.

### <a name="example"></a>Пример

См. раздел [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) с примером объявления и использования `streambuf_type`.

## <a name="traits_type"></a>  ostreambuf_iterator::traits_type

Тип, обеспечивающий тип признаков символа для `ostream_iterator`.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Заметки

Этот тип является синонимом для параметра шаблона `Traits`.

### <a name="example"></a>Пример

```cpp
// ostreambuf_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostreambuf_iterator<char>::char_type CHT1;
   typedef ostreambuf_iterator<char>::traits_type CHTR1;

   // ostreambuf_iterator for stream cout
   // with new line delimiter:
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );

   // Standard iterator interface for writing
   // elements to the output streambuf:
   cout << "The characters written to the output stream\n"
        << " by charOutBuf are: ";
*charOutBuf = 'O';
   charOutBuf++;
*charOutBuf = 'U';
   charOutBuf++;
*charOutBuf = 'T';
   charOutBuf++;
   cout << "." << endl;
}
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)

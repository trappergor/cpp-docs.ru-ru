---
title: Класс strstreambuf | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32f5cbc162fbcb6b82676ec782099df80af03eb4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="strstreambuf-class"></a>Класс strstreambuf

Описывает буфер потока, который управляет передачей элементов из последовательности элементов, содержащейся в объекте массива `char`, и в эту последовательность.

## <a name="syntax"></a>Синтаксис

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Примечания

В зависимости от способа создания объекта он выделяется, расширяется и освобождается при необходимости для обеспечения соответствия изменениям в последовательности.

Объект класса `strstreambuf` хранит несколько битов сведений о режиме в качестве своего режима `strstreambuf`. Эти биты определяют следующие сведения об управляемой последовательности:

- она выделена, и ее со временем нужно освободить;

- ее можно изменять;

- она расширяется за счет перераспределения хранилища;

- она заморожена, поэтому ее необходимо разморозить до уничтожения или освобождения (если он выделен) объекта элементом, отличным от объекта.

Замороженную управляемую последовательность невозможно изменить или расширить независимо от состояния этих отдельных битов режима.

Объект также хранит указатели на две функции, которые управляют выделением `strstreambuf`. Если это пустые указатели, объект использует собственный метод выделения и освобождения памяти для управляемой последовательности.

> [!NOTE]
> Этот класс устарел. Вместо этого следует использовать [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) или [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[strstreambuf](#strstreambuf)|Создает объект типа `strstreambuf`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[freeze](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[overflow](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[str](#str)|Вызывает метод [freeze](#freeze), а затем возвращает указатель на начало управляемой последовательности.|
|[underflow](#underflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="freeze"></a> strstreambuf::freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

`_Freezeit` Объект `bool` , указывающее, следует ли поток, который должен быть зафиксирован.

### <a name="remarks"></a>Примечания

Если `_Freezeit` имеет значение true, функция меняет сохраненный режим `strstreambuf`, чтобы зафиксировать управляемую последовательность. В противном случае управляемая последовательность зафиксирована не будет.

[str](#str) подразумевает `freeze`.

> [!NOTE]
> Замороженные буферы не будут освобождены во время уничтожения `strstreambuf`. Необходимо отменить фиксацию буфера до освобождения, чтобы избежать утечки памяти.

### <a name="example"></a>Пример

```cpp
// strstreambuf_freeze.cpp
// compile with: /EHsc

#include <iostream>
#include <strstream>

using namespace std;

void report(strstream &x)
{
    if (!x.good())
        cout << "stream bad" << endl;
    else
        cout << "stream good" << endl;
}

int main()
{
    strstream x;

    x << "test1";
    cout << "before freeze: ";
    report(x);

    // Calling str freezes stream.
    cout.write(x.rdbuf()->str(), 5) << endl;
    cout << "after freeze: ";
    report(x);

    // Stream is bad now, wrote on frozen stream
    x << "test1.5";
    cout << "after write to frozen stream: ";
    report(x);

    // Unfreeze stream, but it is still bad
    x.rdbuf()->freeze(false);
    cout << "after unfreezing stream: ";
    report(x);

    // Clear stream
    x.clear();
    cout << "after clearing stream: ";
    report(x);

    x << "test3";
    cout.write(x.rdbuf()->str(), 10) << endl;

    // Clean up.  Failure to unfreeze stream will cause a
    // memory leak.
    x.rdbuf()->freeze(false);
}
```

```Output
before freeze: stream good
test1
after freeze: stream good
after write to frozen stream: stream bad
after unfreezing stream: stream bad
after clearing stream: stream good
test1test3
```

## <a name="overflow"></a> strstreambuf::overflow

Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

`_Meta` Символ, который необходимо вставить в буфер, или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, если _ *Meta* == `EOF`, возвращается другое значение, отличное от `EOF`. В противном случае возвращается значение \_ *Meta*.

### <a name="remarks"></a>Примечания

Если _ *Meta* != `EOF`, защищенная виртуальная функция-член пытается вставить элемент (`char`)\_ *Meta* в выходной буфер. Для этого существует несколько способов.

- Если позиция записи доступна, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Если сохраненный режим strstreambuf указывает, что управляемая последовательность доступна для изменения и расширения и не зафиксирована, функция может сделать позицию записи доступной, выделив новую позицию для выходного буфера. Расширение выходного буфера таким способом также расширяет любой связанный входной буфер.

## <a name="pbackfail"></a> strstreambuf::pbackfail

Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

`_Meta` Символ, который необходимо вставить в буфер, или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, если _ *Meta* == `EOF`, возвращается другое значение, отличное от `EOF`. В противном случае возвращается значение \_ *Meta*.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается поместить элемент обратно во входной буфер, а затем делает его текущим (на него указывает следующий указатель).

Если _ *Meta* == `EOF`, то элемент, который необходимо передать обратно, фактически уже находится в потоке перед текущим элементом. В противном случае элемент заменяется **ch** = (`char`)\_ *Meta*. Функция может передать элемент обратно различными способами.

- Если позиция возврата доступна и сохраненный там элемент оценивается как равный **ch**, функция может уменьшить следующий указатель для входного буфера.

- Если позиция возврата доступна и режим strstreambuf указывает, что управляемая последовательность доступна для изменения, функция может сохранить **ch** в позиции возврата и уменьшить следующий указатель для входного буфера.

## <a name="pcount"></a> strstreambuf::pcount

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

В частности, если [pptr](../standard-library/basic-streambuf-class.md#pptr) является пустым указателем, функция возвращает нуль. В противном случае он возвращает `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase).

### <a name="example"></a>Пример

```cpp
// strstreambuf_pcount.cpp
// compile with: /EHsc
#include <iostream>
#include <strstream>
using namespace std;

int main( )
{
   strstream x;
   x << "test1";
   cout << x.rdbuf( )->pcount( ) << endl;
   x << "test2";
   cout << x.rdbuf( )->pcount( ) << endl;
}
```

## <a name="seekoff"></a> strstreambuf::seekoff

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Off` Позиция поиска для относительно `_Way`.

`_Way` Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности.

Новая позиция определяется следующим образом.

- Если `_Way`  ==  `ios_base::beg`, новая позиция — это начало потока плюс _ *Off*.

- Если `_Way`  ==  `ios_base::cur`, новая позиция — это текущая позиция в потоке плюс _ *Off*.

- Если `_Way`  ==  `ios_base::end`, новая позиция — это конец потока плюс _ *Off*.

Если `_Which` & **ios_base::in** имеет ненулевое значение и существует входной буфер, функция изменяет следующую позицию для чтения во входном буфере. Если `_Which` & **ios_base::out** также имеет ненулевое значение, `_Way` != **ios_base::cur** и существует выходной буфер, функция также задает следующую позицию для записи, соответствующую следующей позиции для чтения.

В противном случае, если `_Which` & `ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="seekpos"></a> strstreambuf::seekpos

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Sp` Позиция для поиска.

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока. Чтобы определить, является ли позиция потока недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности. Новая позиция определяется объектом _ *Sp*.

Если `_Which` & **ios_base::in** имеет ненулевое значение и существует входной буфер, функция изменяет следующую позицию для чтения во входном буфере. Если `_Which` & `ios_base::out` имеет ненулевое значение и существует выходной буфер, функция также задает следующую позицию для записи, соответствующую следующей позиции для чтения. В противном случае, если `_Which` & `ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="str"></a> strstreambuf::str

Вызывает метод [freeze](#freeze), а затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Завершающий элемент null не существует, если явно его не вставить.

### <a name="example"></a>Пример

Пример использования **str** см. в разделе [strstreambuf::freeze](#freeze).

## <a name="strstreambuf"></a> strstreambuf::strstreambuf

Создает объект типа `strstreambuf`.

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* _Allocfunc)(size_t),
    void (* _Freefunc)(void*));

strstreambuf(char* _Getptr,
    streamsize count,
    char* _Putptr = 0);

strstreambuf(signed char* _Getptr,
    streamsize count,
    signed char* _Putptr = 0);

strstreambuf(unsigned char* _Getptr,
    streamsize count,
    unsigned char* _Putptr = 0);

strstreambuf(const char* _Getptr,
    streamsize count);

strstreambuf(const signed char* _Getptr,
    streamsize count);

strstreambuf(const unsigned char* _Getptr,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*_Allocfunc* функция, используемая для выделения буфера памяти.

`count` Определяет длину буфера, на который указывает `_Getptr`. Если `_Getptr` не является аргументом (первая форма конструктора), указан рекомендуемый размер выделения памяти для буферов.

*_Freefunc* функция, используемая для освобождения памяти буфера.

`_Getptr` Буфер, используемый для входных данных.

`_Putptr` Буфер, используемый для вывода.

### <a name="remarks"></a>Примечания

Первый конструктор сохраняет пустой указатель во всех указателях, управляющих входным и выходным буферами, а также распределением strstreambuf. Он задает сохраненный режим strstreambuf, чтобы сделать управляемую последовательность доступной для изменения и расширения. Он также принимает `count` в качестве рекомендуемого первоначального размера выделения.

Второй конструктор ведет себя как первый за исключением того, что он сохраняет _ *Allocfunc* в качестве указателя на функцию, которую необходимо вызвать для распределения хранилища, а \_ *Freefunc* — в качестве указателя на функцию, которую необходимо вызвать для освобождения хранилища.

Три конструктора:

```cpp
strstreambuf(char *_Getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *_Getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *_Getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

также ведут себя как первый за исключением того, что `_Getptr` назначает объект массива, используемый для хранения управляемой последовательности. (Следовательно, он не должен являться пустым указателем.) Число элементов *N* в массиве определяется следующим способом.

- Если (`count` > 0), затем *N* — `count`.

- Если (`count` == 0), затем *N* — `strlen`(( **const** `char` *) `_Getptr` ).

- Если (`count` < 0), затем *N* — **INT_MAX**.

Если `_Putptr` является пустым указателем, функция устанавливает только входной буфер, выполняя следующее.

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

В противном случае она устанавливает и входной, и выходной буферы, выполняя следующее.

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

В этом случае `_Putptr` должен быть в интервале [`_Getptr`, `_Getptr` + *N*].

Наконец, три конструктора:

```cpp
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```

все ведут себя так же как:

```cpp
streambuf((char *)_Getptr, count);
```

за исключением того, что хранимый режим делает управляемую последовательность недоступной для изменения или расширения.

## <a name="underflow"></a> strstreambuf::underflow

Защищенная виртуальная функция для извлечения текущего элемента из входного потока.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае она возвращает текущий элемент во входном потоке, преобразованный, как описано выше.

### <a name="remarks"></a>Примечания

Защищенные виртуальной функции-члена написана для извлечения текущего элемента **ch** из входного буфера, перейти на позицию в текущем потоке и возвращает имя элемента (`int`) (`unsigned char`) **ch** . Это можно сделать единственным способом: если позиция чтения доступна, функция принимает **ch** в качестве элемента, хранящегося в этой позиции чтения, и перемещает вперед следующий указатель для входного буфера.

## <a name="see-also"></a>См. также

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>

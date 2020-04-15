---
title: Класс strstreambuf
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
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
ms.openlocfilehash: 28399a1cd55407aadbc5d59e1e835892218ad0c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376612"
---
# <a name="strstreambuf-class"></a>Класс strstreambuf

Описывает буфер потока, который контролирует передачу элементов и из последовательности элементов, хранящихся в объекте **массива символа.**

## <a name="syntax"></a>Синтаксис

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Remarks

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

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Заморозить](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[Переполнения](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.|
|[Ул](#str)|Вызывает [freeze](#freeze), затем возвращает указатель на начало управляемой последовательности.|
|[недотека](#underflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="strstreambuffreeze"></a><a name="freeze"></a>strstreambuf::freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

*_Freezeit*\
**Bool** с указанием, хотите ли вы, чтобы поток был заморожен.

### <a name="remarks"></a>Remarks

Если *_Freezeit* верно, функция изменяет `strstreambuf` режим хранения, чтобы сделать контролируемую последовательность замороженной. В противном случае управляемая последовательность зафиксирована не будет.

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

## <a name="strstreambufoverflow"></a><a name="overflow"></a>strstreambuf::overflow

Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

*_meta*\
Символ для вставки в буфер или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, == `EOF`если * \_Мета* `EOF`, он возвращает некоторые значения, кроме . В противном * \_* случае, он возвращает Мета .

### <a name="remarks"></a>Remarks

Если * \_Meta* `EOF`! » , защищенная функция `(char)_Meta` виртуального члена пытается вставить элемент в буфер вывода. Это можно сделать разными способами.

- Если позиция записи доступна, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Если сохраненный режим strstreambuf указывает, что управляемая последовательность доступна для изменения и расширения и не зафиксирована, функция может сделать позицию записи доступной, выделив новую позицию для выходного буфера. Расширение выходного буфера таким способом также расширяет любой связанный входной буфер.

## <a name="strstreambufpbackfail"></a><a name="pbackfail"></a>strstreambuf::pbackfail

Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Параметры

*_meta*\
Символ для вставки в буфер или `EOF`.

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае, == `EOF`если * \_Мета* `EOF`, он возвращает некоторые значения, кроме . В противном * \_* случае, он возвращает Мета .

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член пытается поместить элемент обратно во входной буфер, а затем делает его текущим (на него указывает следующий указатель).

Если * \_Мета* == `EOF`, элемент для отодвигая фактически один уже в потоке до текущего элемента. В противном случае `ch = (char)_Meta`этот элемент заменяется . Функция может передать элемент обратно различными способами.

- Если позиция возврата доступна, и элемент, хранящийся там, сравнивается `ch`с, он может дебыстрее следующего указателя для буфера ввода.

- Если позиция возврата доступна, и если режим strstreambuf говорит, что контролируемая `ch` последовательность изменяется, функция может хранить в позиции возврата и детрирование следующего указателя для буфера ввода.

## <a name="strstreambufpcount"></a><a name="pcount"></a>strstreambuf::pсчет

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Remarks

В частности, если [pptr](../standard-library/basic-streambuf-class.md#pptr) является пустым указателем, функция возвращает нуль. В противном `pptr`  - случае, он возвращает [pbase](../standard-library/basic-streambuf-class.md#pbase).

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

## <a name="strstreambufseekoff"></a><a name="seekoff"></a>strstreambuf::seekoff

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_off*\
Положение, чтобы искать относительно *_Way*.

*_Way*\
Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

*_which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока.

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности.

Новая позиция определяется следующим образом.

- Если, `_Way == ios_base::beg`новая позиция является началом потока плюс *_Off*.

- Если `_Way == ios_base::cur`новая позиция — это текущее положение потока плюс *_Off.*

- Если `_Way == ios_base::end`новая позиция является концом потока плюс *_Off.*

Если `_Which & ios_base::in` нетвера и буфер ввода существует, функция изменяет следующую позицию для чтения в буфере ввода. Если `_Which & ios_base::out` также нетно, `_Way != ios_base::cur`и буфер вывода существует, функция также устанавливает следующую позицию, чтобы написать, чтобы соответствовать следующей позиции для чтения.

В противном случае, если `_Which & ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="strstreambufseekpos"></a><a name="seekpos"></a>strstreambuf::seekpos

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Sp*\
Позиция для поиска.

*_which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно изменила одну или обе позиции потока, то она возвращает итоговую позицию потока. В противном случае она завершается неудачно и возвращает недопустимую позицию потока. Чтобы определить, является ли позиция в потоке недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член пытается изменить текущие положения для управляемых потоков. Для объекта класса strstreambuf позиция потока состоит исключительно из смещения потока. Нулевое смещение обозначает первый элемент управляемой последовательности. Новая позиция определяется *_Sp.*

Если `_Which` & **ios_base::in** имеет ненулевое значение и существует входной буфер, функция изменяет следующую позицию для чтения во входном буфере. Если `_Which` & `ios_base::out` имеет ненулевое значение и существует выходной буфер, функция также задает следующую позицию для записи, соответствующую следующей позиции для чтения. В противном случае, если `_Which` & `ios_base::out` имеет ненулевое значение и выходной буфер существует, функция меняет следующую позицию для записи в выходном буфере. В противном случае операция размещения завершается сбоем. Для успешного выполнения операции размещения итоговая позиция потока должна находиться в управляемой последовательности.

## <a name="strstreambufstr"></a><a name="str"></a>strstreambuf::str

Вызывает [freeze](#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Remarks

Завершающий элемент null не существует, если явно его не вставить.

### <a name="example"></a>Пример

Пример использования **str** см. в разделе [strstreambuf::freeze](#freeze).

## <a name="strstreambufstrstreambuf"></a><a name="strstreambuf"></a>strstreambuf::strstreambuf

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

*_Allocfunc*\
Функция, используемая для выделения памяти буфера.

*Рассчитывать*\
Определяет длину буфера, на который указывает *_Getptr.* Если *_Getptr* не является аргументом (первая форма конструктора), предлагаемый размер распределения для буферов.

*_Freefunc*\
Функция, используемая для освобождения памяти буфера.

*_Getptr*\
Буфер, используемый для ввода.

*_Putptr*\
Буфер, используемый для вывода.

### <a name="remarks"></a>Remarks

Первый конструктор сохраняет пустой указатель во всех указателях, управляющих входным и выходным буферами, а также распределением strstreambuf. Он задает сохраненный режим strstreambuf, чтобы сделать управляемую последовательность доступной для изменения и расширения. Он также принимает *подсчет* в качестве предполагаемого первоначального размера распределения.

Второй конструктор ведет себя как первый, за исключением того, что он хранит * \_Allocfunc* в качестве указателя на функцию для выделения для выделения хранения и * \_Freefunc* в качестве указателя на функцию, чтобы вызвать, чтобы освободить это хранилище.

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

также ведут себя как первый за исключением того, что `_Getptr` назначает объект массива, используемый для хранения управляемой последовательности. (Следовательно, он не должен быть нулевым указателем.) Количество элементов *N* в массиве определяется следующим образом:

- Если`count` (> 0), `count`то *N* .

- Если`count` (No 0), то `strlen` *N* **(конст)** `char` ). `_Getptr`

- Если`count` (< 0), то *N* **INT_MAX**.

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

## <a name="strstreambufunderflow"></a><a name="underflow"></a>strstreambuf::underflow

Защищенная виртуальная функция для извлечения текущего элемента из входного потока.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение `EOF`. В противном случае она возвращает текущий элемент во входном потоке, преобразованный, как описано выше.

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена стремится `ch` извлечь текущий элемент из входного буфера, затем`int`продвинуть`unsigned char`текущее положение потока и вернуть элемент как ( () **ч.** Он может сделать это только одним способом: если `ch` позиция чтения доступна, он принимает как элемент, хранящийся в положении чтения и продвигает следующий указатель для буфера ввода.

## <a name="see-also"></a>См. также раздел

[Streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)

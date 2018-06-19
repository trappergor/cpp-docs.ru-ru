---
title: Класс basic_streambuf | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- streambuf/std::basic_streambuf
- streambuf/std::basic_streambuf::char_type
- streambuf/std::basic_streambuf::int_type
- streambuf/std::basic_streambuf::off_type
- streambuf/std::basic_streambuf::pos_type
- streambuf/std::basic_streambuf::traits_type
- streambuf/std::basic_streambuf::eback
- streambuf/std::basic_streambuf::egptr
- streambuf/std::basic_streambuf::epptr
- streambuf/std::basic_streambuf::gbump
- streambuf/std::basic_streambuf::getloc
- streambuf/std::basic_streambuf::gptr
- streambuf/std::basic_streambuf::imbue
- streambuf/std::basic_streambuf::in_avail
- streambuf/std::basic_streambuf::overflow
- streambuf/std::basic_streambuf::pbackfail
- streambuf/std::basic_streambuf::pbase
- streambuf/std::basic_streambuf::pbump
- streambuf/std::basic_streambuf::pptr
- streambuf/std::basic_streambuf::pubimbue
- streambuf/std::basic_streambuf::pubseekoff
- streambuf/std::basic_streambuf::pubseekpos
- streambuf/std::basic_streambuf::pubsetbuf
- streambuf/std::basic_streambuf::pubsync
- streambuf/std::basic_streambuf::sbumpc
- streambuf/std::basic_streambuf::seekoff
- streambuf/std::basic_streambuf::seekpos
- streambuf/std::basic_streambuf::setbuf
- streambuf/std::basic_streambuf::setg
- streambuf/std::basic_streambuf::setp
- streambuf/std::basic_streambuf::sgetc
- streambuf/std::basic_streambuf::sgetn
- streambuf/std::basic_streambuf::showmanyc
- streambuf/std::basic_streambuf::snextc
- streambuf/std::basic_streambuf::sputbackc
- streambuf/std::basic_streambuf::sputc
- streambuf/std::basic_streambuf::sputn
- streambuf/std::basic_streambuf::stossc
- streambuf/std::basic_streambuf::sungetc
- streambuf/std::basic_streambuf::swap
- streambuf/std::basic_streambuf::sync
- streambuf/std::basic_streambuf::uflow
- streambuf/std::basic_streambuf::underflow
- streambuf/std::basic_streambuf::xsgetn
- streambuf/std::basic_streambuf::xsputn
dev_langs:
- C++
helpviewer_keywords:
- std::basic_streambuf [C++]
- std::basic_streambuf [C++], char_type
- std::basic_streambuf [C++], int_type
- std::basic_streambuf [C++], off_type
- std::basic_streambuf [C++], pos_type
- std::basic_streambuf [C++], traits_type
- std::basic_streambuf [C++], eback
- std::basic_streambuf [C++], egptr
- std::basic_streambuf [C++], epptr
- std::basic_streambuf [C++], gbump
- std::basic_streambuf [C++], getloc
- std::basic_streambuf [C++], gptr
- std::basic_streambuf [C++], imbue
- std::basic_streambuf [C++], in_avail
- std::basic_streambuf [C++], overflow
- std::basic_streambuf [C++], pbackfail
- std::basic_streambuf [C++], pbase
- std::basic_streambuf [C++], pbump
- std::basic_streambuf [C++], pptr
- std::basic_streambuf [C++], pubimbue
- std::basic_streambuf [C++], pubseekoff
- std::basic_streambuf [C++], pubseekpos
- std::basic_streambuf [C++], pubsetbuf
- std::basic_streambuf [C++], pubsync
- std::basic_streambuf [C++], sbumpc
- std::basic_streambuf [C++], seekoff
- std::basic_streambuf [C++], seekpos
- std::basic_streambuf [C++], setbuf
- std::basic_streambuf [C++], setg
- std::basic_streambuf [C++], setp
- std::basic_streambuf [C++], sgetc
- std::basic_streambuf [C++], sgetn
- std::basic_streambuf [C++], showmanyc
- std::basic_streambuf [C++], snextc
- std::basic_streambuf [C++], sputbackc
- std::basic_streambuf [C++], sputc
- std::basic_streambuf [C++], sputn
- std::basic_streambuf [C++], stossc
- std::basic_streambuf [C++], sungetc
- std::basic_streambuf [C++], swap
- std::basic_streambuf [C++], sync
- std::basic_streambuf [C++], uflow
- std::basic_streambuf [C++], underflow
- std::basic_streambuf [C++], xsgetn
- std::basic_streambuf [C++], xsputn
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7453120d40efc05fd0dce919a7b85869710a9b18
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848915"
---
# <a name="basicstreambuf-class"></a>Класс basic_streambuf

Описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_streambuf;
```

### <a name="parameters"></a>Параметры

`Elem` Объект [char_type](#char_type).

`Tr` Символ [traits_type](#traits_type).

## <a name="remarks"></a>Примечания

Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него. Объект класса `basic_streambuf` помогает управлять потоком с элементами типа `Tr`, также называемого [char_type](#char_type), у которого признаки символа определяются классом [char_traits](../standard-library/char-traits-struct.md), также известным как [traits_type](#traits_type).

В теории каждый буфер потока управляет двумя независимыми потоками: один для извлечения (ввод) и один для вставки (вывод). Однако конкретное представление может запретить один или оба эти потока. Обычно он поддерживает определенные связи между двумя потоками. То, что вы вставляете в выходной поток [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, например объект `Tr`>, вы позже извлекаете из его входного потока. При размещении одного потока объекта [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem` `Tr`> вы размещаете второй поток для образования тандема.

Общий интерфейс для класса шаблона `basic_streambuf` предоставляет операции, которые являются общими для всех буферов потока, однако имеют специализацию. Защищенный интерфейс предоставляет операции, необходимые конкретному представлению потока для выполнения назначенной ему работы. Защищенная виртуальная функция-член позволяет точно настроить поведение производного буфера потока для конкретного представления потока. Каждый производный буфер потока в этой библиотеке описывает, как он специализирует поведение его защищенных виртуальных функций-членов. Поведение по умолчанию для базового класса, которое обычно заключается в бездействии, описано в этом разделе.

Оставшиеся защищенные функции-члены управляют копированием в любое хранилище, предоставленное для буферизации операций обмена данными с потоками, и из него. Входной буфер, например, характеризуется следующим:

- [eback](#eback) — указатель на начало буфера;

- [gptr](#gptr) — указатель на следующий элемент для чтения;

- [egptr](#egptr) — указатель на позицию сразу после конца буфера.

Аналогичным образом выходной буфер характеризуется следующим:

- [pbase](#pbase) — указатель на начало буфера;

- [pptr](#pptr) — указатель на следующий элемент для записи;

- [epptr](#epptr) — указатель на позицию сразу после конца буфера.

Для любого буфера применяется следующий протокол.

- Если следующий указатель имеет значение NULL, буфер не существует. В противном случае все три указателя указывают на одну и ту же последовательность. Их можно безопасно сравнивать с точки зрения порядка.

- Если для выходного буфера следующий указатель при сравнении дает значение меньше конечного указателя, можно сохранить элемент в позиции записи, обозначенной следующим указателем.

- Если для входного буфера следующий указатель при сравнении дает значение меньше конечного указателя, можно считать элемент в позиции чтения, обозначенной следующим указателем.

- Если для входного буфера начальный указатель при сравнении дает значение меньше следующего указателя, можно возвратить элемент в позицию возврата, обозначенную следующим указателем, значение которого уменьшено.

Все защищенные виртуальные функции-члены, записываемые для класса, являющегося производным от `basic_streambuf`< `Elem`, `Tr`>, должны взаимодействовать в соответствии с этим протоколом.

Объект класса `basic_streambuf`< `Elem`, `Tr`> хранит шесть описанных выше указателей. Он также хранит объект языкового стандарта в объекте типа [locale](../standard-library/locale-class.md), чтобы им при необходимости мог воспользоваться производный буфер потока.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_streambuf](#basic_streambuf)|Создает объект типа `basic_streambuf`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Связывает имя типа с параметром шаблона `Elem`.|
|[int_type](#int_type)|Сопоставляет имя типа в области `basic_streambuf` с параметром шаблона `Elem`.|
|[off_type](#off_type)|Сопоставляет имя типа в области `basic_streambuf` с параметром шаблона `Elem`.|
|[pos_type](#pos_type)|Сопоставляет имя типа в области `basic_streambuf` с параметром шаблона `Elem`.|
|[traits_type](#traits_type)|Связывает имя типа с параметром шаблона `Tr`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[eback](#eback)|Защищенная функция, возвращающая указатель на начало входного буфера.|
|[egptr](#egptr)|Защищенная функция, возвращающая указатель на позицию сразу после конца входного буфера.|
|[epptr](#epptr)|Защищенная функция, возвращающая указатель на позицию сразу после конца выходного буфера.|
|[gbump](#gbump)|Защищенная функция, которая добавляет `count` в следующий указатель для входного буфера.|
|[getloc](#getloc)|Возвращает языковой стандарт объекта `basic_streambuf`.|
|[gptr](#gptr)|Защищенная функция, возвращающая указатель на следующий элемент входного буфера.|
|[imbue](#imbue)|Защищенная виртуальная функция, вызываемая [pubimbue](#pubimbue).|
|[in_avail](#in_avail)|Возвращает количество элементов, готовых к считыванию из буфера.|
|[overflow](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).|
|[pbase](#pbase)|Защищенная функция, возвращающая указатель на начало выходного буфера.|
|[pbump](#pbump)|Защищенная функция, которая добавляет `count` в следующий указатель для выходного буфера.|
|[pptr](#pptr)|Защищенная функция, возвращающая указатель на следующий элемент выходного буфера.|
|[pubimbue](#pubimbue)|Задает языковой стандарт объекта `basic_streambuf`.|
|[pubseekoff](#pubseekoff)|Вызывает [seekoff](#seekoff) — защищенную виртуальную функцию, которая переопределяется в производном классе.|
|[pubseekpos](#pubseekpos)|Вызывает [seekpos](#seekpos) — защищенную виртуальную функцию, которая переопределяется в производном классе, и выполняет сброс текущего положения указателя.|
|[pubsetbuf](#pubsetbuf)|Вызывает [setbuf](#setbuf) — защищенную виртуальную функцию, которая переопределяется в производном классе.|
|[pubsync](#pubsync)|Вызывает [sync](#sync) — защищенную виртуальную функцию, которая переопределяется в производном классе, и обновляет внешний поток, сопоставленный с данным буфером.|
|[sbumpc](#sbumpc)|Считывает и возвращает текущий элемент, перемещая указатель потока.|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[setbuf](#setbuf)|Защищенная виртуальная функция-член выполняет операции, относящиеся непосредственно к каждому производному буферу потока.|
|[setg](#setg)|Защищенная функция, которая сохраняет `_Gbeg` в начальном указателе, `_Gnext` в следующем указателе и `_Gend` в конечном указателе для входного буфера.|
|[setp](#setp)|Защищенная функция, которая сохраняет `_Pbeg` в начальном указателе и `_Pend` в конечном указателе для входного буфера.|
|[sgetc](#sgetc)|Возвращает текущий элемент без изменения положения в потоке.|
|[sgetn](#sgetn)|Возвращает количество считанных элементов.|
|[showmanyc](#showmanyc)|Защищенная виртуальная функция-член, возвращающая число символов, которые могут быть извлечены из входного потока, и обеспечивает отсутствие бесконечного времени ожидания в программе.|
|[snextc](#snextc)|Считывает текущий элемент и возвращает следующий элемент.|
|[sputbackc](#sputbackc)|Помещает `char_type` в поток.|
|[sputc](#sputc)|Помещает символ в поток.|
|[sputn](#sputn)|Помещает строку символов в поток.|
|[stossc](#stossc)|Переходит за текущий элемент в потоке.|
|[sungetc](#sungetc)|Получает символ из потока.|
|[swap](#swap)|Меняет местами значения в этом объекте и значения предоставленного параметра объекта `basic_streambuf`.|
|[sync](#sync)|Защищенная виртуальная функция, которая пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.|
|[uflow](#uflow)|Защищенная виртуальная функция, которая извлекает текущий элемент из входного потока.|
|[underflow](#underflow)|Защищенная виртуальная функция, которая извлекает текущий элемент из входного потока.|
|[xsgetn](#xsgetn)|Защищенная виртуальная функция, которая извлекает элементы из входного потока.|
|[xsputn](#xsputn)|Защищенная виртуальная функция, которая вставляет элементы в выходной поток.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Присваивает значения этому объекту из другого объекта `basic_streambuf`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<streambuf>

**Пространство имен:** std

## <a name="basic_streambuf"></a>  basic_streambuf::basic_streambuf

Создает объект типа `basic_streambuf`.

```cpp
basic_streambuf();

basic_streambuf(const basic_streambuf& right);
```

### <a name="parameters"></a>Параметры

`right` Ссылка lvalue на `basic_streambuf` объект, используемый для задания значений для этого `basic_streambuf` объекта.

### <a name="remarks"></a>Примечания

Первый защищенный конструктор сохраняет указатель null во всех указателях, управляющих входным и выходным буферами. Он также сохраняет `locale::classic` в объекте языкового стандарта. Дополнительные сведения см. в разделе [locale::classic](../standard-library/locale-class.md#classic).

Второй защищенный конструктор копирует указатели и языковой стандарт из `right`.

## <a name="char_type"></a>  basic_streambuf::char_type

Связывает имя типа с параметром шаблона **Elem**.

```cpp
typedef Elem char_type;
```

## <a name="eback"></a>  basic_streambuf::eback

Защищенная функция, возвращающая указатель на начало входного буфера.

```cpp
char_type *eback() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало входного буфера.

## <a name="egptr"></a>  basic_streambuf::egptr

Защищенная функция, возвращающая указатель на позицию сразу после конца входного буфера.

```cpp
char_type *egptr() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на позицию сразу после конца входного буфера.

## <a name="epptr"></a>  basic_streambuf::epptr

Защищенная функция, возвращающая указатель на позицию сразу после конца выходного буфера.

```cpp
char_type *epptr() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на позицию сразу после конца выходного буфера.

## <a name="gbump"></a>  basic_streambuf::gbump

Защищенная функция, которая добавляет `count` в следующий указатель для входного буфера.

```cpp
void gbump(int count);
```

### <a name="parameters"></a>Параметры

`count` Величина, на которую переместить указатель.

## <a name="getloc"></a>  basic_streambuf::getloc

Возвращает языковой стандарт объекта basic_streambuf.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект языкового стандарта.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ios_base::getloc](../standard-library/ios-base-class.md#getloc).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_getloc.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << cout.rdbuf( )->getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="gptr"></a>  basic_streambuf::gptr

Защищенная функция, возвращающая указатель на следующий элемент входного буфера.

```cpp
char_type *gptr() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент входного буфера.

## <a name="imbue"></a>  basic_streambuf::imbue

Защищенная виртуальная функция, вызываемая объектом [pubimbue](#pubimbue).

```cpp
virtual void imbue(const locale& _Loc);
```

### <a name="parameters"></a>Параметры

`_Loc` Ссылка на языковой стандарт.

### <a name="remarks"></a>Примечания

По умолчанию не нужно ничего делать.

## <a name="in_avail"></a>  basic_streambuf::in_avail

Возвращает количество элементов, готовых к считыванию из буфера.

```cpp
streamsize in_avail();
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, готовых к считыванию из буфера.

### <a name="remarks"></a>Примечания

Если [позицию чтения](../standard-library/basic-streambuf-class.md) доступен, функция-член возвращает [egptr](#egptr) - [gptr](#gptr). В противном случае она возвращает [showmanyc](#showmanyc).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_in_avail.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   char c;
   // cin's buffer is empty, in_avail will return 0
   cout << cin.rdbuf( )->in_avail( ) << endl;
   cin >> c;
   cout << cin.rdbuf( )->in_avail( ) << endl;
}
```

## <a name="int_type"></a>  basic_streambuf::int_type

Связывает имя типа в пределах области basic_streambuf с одним из типов в параметре шаблона.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a>  basic_streambuf::off_type

Связывает имя типа в пределах области basic_streambuf с одним из типов в параметре шаблона.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="op_eq"></a>  basic_streambuf::operator=

Присваивает значения этому объекту из другого объекта `basic_streambuf`.

```cpp
basic_streambuf& operator=(const basic_streambuf& right);
```

### <a name="parameters"></a>Параметры

`right` Ссылка lvalue на `basic_streambuf` объект, используемый для присвоения значений этого объекта.

### <a name="remarks"></a>Примечания

Защищенный оператор-член элемент копирует из `right` указатели, которые управляют входным и выходным буфером. Он также сохраняет `right.`[getloc()](#getloc) в `locale object`. Он возвращает `*this`.

## <a name="overflow"></a>  basic_streambuf::overflow

Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Параметры

`_Meta` Символ, который необходимо вставить в буфер, или **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Возвращаемое значение

Если функция не может выполниться успешно, она возвращает **traits_type::eof** или создает исключение. В противном случае она возвращает **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*). Поведением по умолчанию является возврат **traits_type::eof**.

### <a name="remarks"></a>Примечания

Если _ *Meta* при сравнении не дает значение, равное **traits_type::eof**, защищенная виртуальная функция-член пытается вставить элемент **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) в выходной поток. Для этого существует несколько способов.

- Если объект `write position` доступен, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Можно сделать позицию записи доступной, выделяя новое или дополнительное хранилище для выходного буфера.

- Можно сделать позицию записи доступной, выписав в какое-либо внешнее место назначения некоторые или все элементы между началом и следующими указателями для выходного буфера.

Функция виртуального переполнения вместе с функциями [sync](#sync) и [underflow](#underflow) определяет характеристики класса, производного от streambuf. Каждый производный класс может реализовать переполнение по-разному, но интерфейс с классом вызывающего потока одинаков.

Функция `overflow` наиболее часто вызывается общими функциями `streambuf`, такими как `sputc` и `sputn`, когда область put заполнена, но другие классы, включая классы потоков, могут вызывать `overflow` в любое время.

Функция использует символы в области put между указателями `pbase` и `pptr`, а затем повторно инициализирует область put. Функция `overflow` должна также использовать `nCh` (если `nCh` не `EOF`), или она может выбрать поместить этот символ в новую область put, чтобы он использовался при следующем вызове.

Определение использования разное в разных производных классах. Например, класс `filebuf` записывает свои символы в файл, а класс `strstreambuf` сохраняет их в своем буфере и (если буфер обозначен как динамический) разворачивает этот буфер в ответ на вызов переполнения. Это расширение достигается освобождением старого буфера и его замены на новый буфер большего размера. Указатели настраиваются по необходимости.

## <a name="pbackfail"></a>  basic_streambuf::pbackfail

Защищенная виртуальная функция-член, которая пытается поместить элемент обратно во входной поток, а затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Параметры

`_Meta` Символ, который необходимо вставить в буфер, или **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

### <a name="return-value"></a>Возвращаемое значение

Если функция не может выполниться успешно, она возвращает **traits_type::eof** или создает исключение. В противном случае возвращается другое значение. Поведением по умолчанию является возврат **traits_type::eof**.

### <a name="remarks"></a>Примечания

Если _ *Meta* при сравнении дает значение, равное **traits_type::eof**, то элемент, который необходимо передать обратно, фактически уже в потоке перед текущим элементом. В противном случае этот элемент заменяется **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*). Функция может передать элемент обратно различными способами.

- Если позиция возврата доступна, функция может сохранить элемент в позиции возврата и уменьшить следующий указатель для входного буфера.

- Можно сделать позицию возврата доступной, выделяя новое или дополнительное хранилище для входного буфера.

- Для буфера потока с общими входным и выходным потоками можно сделать позицию возврата доступной, выписав в какое-либо внешнее место назначения некоторые или все элементы между началом и следующими указателями для выходного буфера.

## <a name="pbase"></a>  basic_streambuf::pbase

Защищенная функция, возвращающая указатель на начало выходного буфера.

```cpp
char_type *pbase() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало выходного буфера.

## <a name="pbump"></a>  basic_streambuf::pbump

Защищенная функция, которая добавляет `count` в следующий указатель для выходного буфера.

```cpp
void pbump(int count);
```

### <a name="parameters"></a>Параметры

`count` Число символов, которое необходимо переместить вперед позиции записи.

## <a name="pos_type"></a>  basic_streambuf::pos_type

Связывает имя типа в пределах области basic_streambuf с одним из типов в параметре шаблона.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="pptr"></a>  basic_streambuf::pptr

Защищенная функция, возвращающая указатель на следующий элемент выходного буфера.

```cpp
char_type *pptr() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент выходного буфера.

## <a name="pubimbue"></a>  basic_streambuf::pubimbue

Устанавливает языковой стандарт объекта basic_streambuf.

```cpp
locale pubimbue(const locale& _Loc);
```

### <a name="parameters"></a>Параметры

`_Loc` Ссылка на языковой стандарт.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение, хранящееся в объекте языкового стандарта.

### <a name="remarks"></a>Примечания

Функция-член сохраняет _ *Loc* в объекте языкового стандарта и вызывает [imbue](#imbue).

### <a name="example"></a>Пример

Пример, в котором используется `pubimbue`, см. в разделе [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue).

## <a name="pubseekoff"></a>  basic_streambuf::pubseekoff

Вызывает [seekoff](#seekoff) — защищенную виртуальную функцию, которая переопределяется в производном классе.

```cpp
pos_type pubseekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Off` Позиция поиска для относительно `_Way`.

`_Way` Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую позицию или недопустимую позицию в потоке ([seekoff](#seekoff)(_ *Off*, `_Way`, `_Which`)).

### <a name="remarks"></a>Примечания

Перемещает указатель относительно `_Way`.

## <a name="pubseekpos"></a>  basic_streambuf::pubseekpos

Вызывает [seekpos](#seekpos) — защищенную виртуальную функцию, которая переопределяется в производном классе, и выполняет сброс текущего положения указателя.

```cpp
pos_type pubseekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Sp` Позиция для поиска.

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую позицию или недопустимую позицию в потоке. Чтобы определить, является ли позиция потока недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Примечания

Функция-член возвращает [seekpos](#seekpos)(_ *Sp*, `_Which`).

## <a name="pubsetbuf"></a>  basic_streambuf::pubsetbuf

Вызывает [setbuf](#setbuf) — защищенную виртуальную функцию, которая переопределяется в производном классе.

```cpp
basic_streambuf<Elem, Tr> *pubsetbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Параметры

`_Buffer` Указатель на `char_type` для этого экземпляра.

`count` Размер буфера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает [setbuf](#setbuf)(`_Buffer`, `count`).

## <a name="pubsync"></a>  basic_streambuf::pubsync

Вызывает [sync](#sync) — защищенную виртуальную функцию, которая переопределяется в производном классе, и обновляет внешний поток, сопоставленный с данным буфером.

```cpp
int pubsync();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [синхронизации](#sync) или -1, если сбой.

## <a name="sbumpc"></a>  basic_streambuf::sbumpc

Считывает и возвращает текущий элемент, перемещая указатель потока.

```cpp
int_type sbumpc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий элемент.

### <a name="remarks"></a>Примечания

Если позиция чтения доступна, функция-член возвращает **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **\****[gptr](#gptr)) и увеличивает следующий указатель для входного буфера. В противном случае возвращается [uflow](#uflow).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sbumpc.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 0;
   i = cin.rdbuf( )->sbumpc( );
   cout << i << endl;
}
```

```Output

3

```

```Output

      33
51
```

## <a name="seekoff"></a>  basic_streambuf::seekoff

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Off` Позиция поиска для относительно `_Way`.

`_Way` Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую позицию или недопустимую позицию в потоке (`seekoff`(_ *Off*, `_Way`, `_Which`)).

### <a name="remarks"></a>Примечания

Новая позиция определяется следующим образом.

- Если `_Way`  ==  `ios_base::beg`, новая позиция — это начало потока плюс _ *Off*.

- Если `_Way`  ==  `ios_base::cur`, новая позиция — это текущая позиция в потоке плюс _ *Off*.

- Если `_Way`  ==  `ios_base::end`, новая позиция — это конец потока плюс _ *Off*.

Как правило, если **which & ios_base::in** имеет ненулевое значение, то затрагивается входной поток, а если **which & ios_base::out** имеет ненулевое значение, затрагивается выходной поток. Однако фактическое использование этого параметра меняется в зависимости от буферов производного потока.

Если функция успешно выполняет изменение позиции или позиций в потоке, она возвращает итоговую позицию в потоке или одну из итоговых позиций в потоке. В противном случае она возвращает недопустимую позицию в потоке. По умолчанию возвращается недопустимая позиция в потоке.

## <a name="seekpos"></a>  basic_streambuf::seekpos

Защищенная виртуальная функция-член, которая пытается изменить текущие положения управляемых потоков.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

`_Sp` Позиция для поиска.

`_Which` Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Новая позиция или недопустимая позиция в потоке. Чтобы определить, является ли позиция в потоке недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Примечания

Новая позиция — _ *Sp*.

Как правило, если **which & ios_base::in** имеет ненулевое значение, то затрагивается входной поток, а если **which & ios_base::out** имеет ненулевое значение, затрагивается выходной поток. Однако фактическое использование этого параметра меняется в зависимости от буферов производного потока.

Если функция успешно выполняет изменение позиции или позиций в потоке, она возвращает итоговую позицию в потоке или одну из итоговых позиций в потоке. В противном случае она возвращает недопустимую позицию в потоке (–1). По умолчанию возвращается недопустимая позиция в потоке.

## <a name="setbuf"></a>  basic_streambuf::setbuf

Защищенная виртуальная функция-член выполняет операцию, относящуюся непосредственно к каждому производному буферу потока.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Параметры

`_Buffer` Указатель на буфер.

`count` Размер буфера.

### <a name="return-value"></a>Возвращаемое значение

По умолчанию возвращается **this**.

### <a name="remarks"></a>Примечания

См. [basic_filebuf](../standard-library/basic-filebuf-class.md). `setbuf` предоставляет область памяти для использования объектом `streambuf`. Способ использования буфера задается в производных классах.

## <a name="setg"></a>  basic_streambuf::setg

Защищенная функция, которая сохраняет _ *Gbeg* в начальном указателе, `_Gnext` в следующем указателе и `_Gend` в конечном указателе для входного буфера.

```cpp
void setg(char_type* _Gbeg,
    char_type* _Gnext,
    char_type* _Gend);
```

### <a name="parameters"></a>Параметры

*_Gbeg* указатель на начало буфера.

`_Gnext` Указатель на другом середине буфера.

`_Gend` Указатель конца буфера.

## <a name="setp"></a>  basic_streambuf::setp

Защищенная функция, которая сохраняет `_Pbeg` в начальном указателе и `_Pend` в конечном указателе для входного буфера.

```cpp
void setp(char_type* _Pbeg, char_type* _Pend);
```

### <a name="parameters"></a>Параметры

`_Pbeg` Указатель на начало буфера.

`_Pend` Указатель конца буфера.

## <a name="sgetc"></a>  basic_streambuf::sgetc

Возвращает текущий элемент без изменения положения в потоке.

```cpp
int_type sgetc();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий элемент.

### <a name="remarks"></a>Примечания

Если позиция чтения доступна, функция-член возвращает **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`*`[gptr](#gptr)). В противном случае она возвращает [underflow](#underflow).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sgetc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   ifstream myfile( "basic_streambuf_sgetc.txt", ios::in );

   char i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
   i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
}
```

## <a name="sgetn"></a>  basic_streambuf::sgetn

Извлекает до `count` символов из входного буфера и сохраняет их в предоставленном буфере `ptr`.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.

```cpp
streamsize sgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Параметры

`ptr` Буфер для хранения извлеченных символов.

`count` Количество элементов для чтения.

### <a name="return-value"></a>Возвращаемое значение

Количество считанных элементов. Дополнительные сведения см. в разделе [streamsize](../standard-library/ios-typedefs.md#streamsize).

### <a name="remarks"></a>Примечания

Функция-член возвращает значение [xsgetn](#xsgetn)(`ptr`, `count`).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sgetn.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    ifstream myfile("basic_streambuf_sgetn.txt", ios::in);
    char a[10];

    // Extract 3 characters from myfile and store them in a.
    streamsize i = myfile.rdbuf()->sgetn(&a[0], 3);  // C4996
    a[i] = myfile.widen('\0');

    // Display the size and contents of the buffer passed to sgetn.
    cout << i << " " << a << endl;

    // Display the contents of the original input buffer.
    cout << myfile.rdbuf() << endl;
}
```

## <a name="showmanyc"></a>  basic_streambuf::showmanyc

Защищенная виртуальная функция-член, возвращающая число символов, которые могут быть извлечены из входного потока, и обеспечивающая отсутствие бесконечного времени ожидания в программе.

```cpp
virtual streamsize showmanyc();
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию возвращается ноль.

## <a name="snextc"></a>  basic_streambuf::snextc

Считывает текущий элемент и возвращает следующий элемент.

```cpp
int_type snextc();
```

### <a name="return-value"></a>Возвращаемое значение

Следующий элемент в потоке.

### <a name="remarks"></a>Примечания

Функция-член вызывает [sbumpc](#sbumpc), и если эта функция возвращает **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), то возвращает **traits_type::eof**. В противном случае она возвращает [sgetc](#sgetc).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_snextc.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   int i = 0;
   i = cin.rdbuf( )->snextc( );
   // cout << ( int )char_traits<char>::eof << endl;
   cout << i << endl;
}
```

```Output

aa

```

```Output

aa97
```

## <a name="sputbackc"></a>  basic_streambuf::sputbackc

Помещает char_type в поток.

```cpp
int_type sputbackc(char_type _Ch);
```

### <a name="parameters"></a>Параметры

`_Ch` Символ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает символ или ошибку.

### <a name="remarks"></a>Примечания

Если позиция возврата доступна и `_Ch` при сравнении дает значение, равное символу, хранящемуся в этой позиции, функция-член уменьшает указатель для входного буфера и возвращает **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`_Ch`). В противном случае она возвращает [pbackfail](#pbackfail)(`_Ch`).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sputbackc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;

    ifstream myfile("basic_streambuf_sputbackc.txt",
        ios::in);

    int i = myfile.rdbuf()->sbumpc();
    cout << (char)i << endl;
    int j = myfile.rdbuf()->sputbackc('z');
    if (j == 'z')
    {
        cout << "it worked" << endl;
    }
    i = myfile.rdbuf()->sgetc();
    cout << (char)i << endl;
}
```

## <a name="sputc"></a>  basic_streambuf::sputc

Помещает символ в поток.

```cpp
int_type sputc(char_type _Ch);
```

### <a name="parameters"></a>Параметры

`_Ch` Символ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает символ в случае успешного выполнения.

### <a name="remarks"></a>Примечания

Если `write position` доступна, функция-член сохраняет `_Ch` в позиции записи, увеличивает следующий указатель для выходного буфера и возвращает **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`_Ch`). В противном случае она возвращает [overflow](#overflow)(`_Ch`).

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sputc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   int i = cout.rdbuf( )->sputc( 'a' );
   cout << endl << ( char )i << endl;
}
```

```Output
a
a
```

## <a name="sputn"></a>  basic_streambuf::sputn

Помещает строку символов в поток.

```cpp
streamsize sputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Параметры

`ptr` Строка символов.

`count` Число символов.

### <a name="return-value"></a>Возвращаемое значение

Число символов, фактически вставленных в поток.

### <a name="remarks"></a>Примечания

Функция-член возвращает [xsputn](#xsputn)(`ptr`, `count`). Дополнительные сведения см. в разделе "Примечания" для этой функции-члена.

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sputn.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    streamsize i = cout.rdbuf()->sputn("test", 4);
    cout << endl << i << endl;
}
```

```Output
test
4
```

## <a name="stossc"></a>  basic_streambuf::stossc

Переходит за текущий элемент в потоке.

```cpp
void stossc();
```

### <a name="remarks"></a>Примечания

Эта функция-член вызывает [sbumpc](#sbumpc). Обратите внимание, что для предоставления этой функции-члена реализация не требуется.

### <a name="example"></a>Пример

```cpp
// basic_streambuf_stossc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   ifstream myfile( "basic_streambuf_stossc.txt", ios::in );

   myfile.rdbuf( )->stossc( );
   char i = myfile.rdbuf( )->sgetc( );
   cout << i << endl;
}
```

## <a name="sungetc"></a>  basic_streambuf::sungetc

Получает символ из потока.

```cpp
int_type sungetc();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает символ или ошибку.

### <a name="remarks"></a>Примечания

Если позиция возврата доступна, функция-член увеличивает следующий указатель для входного буфера и возвращает `traits_type::`[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`*`[gptr](#gptr)). Однако не всегда можно определить последний считанный символ, чтобы его можно было записать в состоянии текущего буфера. Если это так, то функция возвращает [pbackfail](#pbackfail). Чтобы избежать такой ситуации, отслеживайте этот символ для возврата и вызывайте функцию `sputbackc(ch)`. Тогда сбоя не произойдет, если вы не будете вызывать ее в начале потока и не будете пытаться вернуть более одного символа.

### <a name="example"></a>Пример

```cpp
// basic_streambuf_sungetc.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ifstream myfile( "basic_streambuf_sungetc.txt", ios::in );

   // Read and increment
   int i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;

   // Read and increment
   i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;

   // Decrement, read, and do not increment
   i = myfile.rdbuf( )->sungetc( );
   cout << ( char )i << endl;

   i = myfile.rdbuf( )->sungetc( );
   cout << ( char )i << endl;

   i = myfile.rdbuf( )->sbumpc( );
   cout << ( char )i << endl;
}
```

## <a name="swap"></a>  basic_streambuf::swap

Меняет местами значения в этом объекте и значения предоставленного объекта `basic_streambuf`.

```cpp
void swap(basic_streambuf& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`right`|Ссылка lvalue на объект `basic_streambuf`, используемый для обмена значений.|

### <a name="remarks"></a>Примечания

Защищенная функция-член выполняет обмен со всеми указателями `right`, управляющими `input buffer` и `output buffer`. Она также выполняет обмен `right.`[getloc()](#getloc) с объектом `locale`.

## <a name="sync"></a>  basic_streambuf::sync

Защищенная виртуальная функция, которая пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Возвращаемое значение

Если функции не удалось выполниться успешно, возвращается значение –1. По умолчанию возвращается ноль.

### <a name="remarks"></a>Примечания

`sync` включает запись всех элементов между началом и следующими указателями для выходного буфера. Она не включает возврат каких-либо элементов между следующим и конечным указателями для входного буфера.

## <a name="traits_type"></a>  basic_streambuf::traits_type

Связывает имя типа с параметром шаблона **Tr**.

```cpp
typedef Tr traits_type;
```

## <a name="uflow"></a>  basic_streambuf::uflow

Защищенная виртуальная функция, которая извлекает текущий элемент из входного потока.

```cpp
virtual int_type uflow();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий элемент.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается извлечь текущий элемент **ch** из входного потока, затем переместить текущую позицию в потоке и возвратить элемент как **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(**ch**). Для этого существует несколько способов.

- Если позиция чтения доступна, она принимает **ch** в качестве элемента, хранящегося в этой позиции чтения, и перемещает следующий указатель для входного буфера.

- Она может считывать элемент непосредственно из внешнего источника и доставлять его в качестве значения **ch**.

- Для буфера потока с общими входным и выходным потоками можно сделать позицию чтения доступной, выписав в какое-либо внешнее место назначения некоторые или все элементы между началом и следующими указателями для выходного буфера. Кроме того, можно выделить новое или дополнительное хранилище для входного буфера. Затем эта функция считывает из внешнего источника один или несколько элементов.

Если функция не может выполниться успешно, она возвращает **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) или создает исключение. В противном случае она возвращает текущий элемент `ch` во входном потоке, преобразованный, как описано выше, и перемещает следующий указатель для входного буфера. Поведение по умолчанию — вызов [underflow](#underflow), и, если эта функция возвращает **traits_type::eof**, возврат **traits_type::eof**. В противном случае функция возвращает текущий элемент **ch** во входном потоке, преобразованный, как описано выше, и перемещает следующий указатель для входного буфера.

## <a name="underflow"></a>  basic_streambuf::underflow

Защищенная виртуальная функция для извлечения текущего элемента из входного потока.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Текущий элемент.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается извлечь текущий элемент **ch** из входного потока без перемещения текущей позиции в потоке и возвратить его как `traits_type::`[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(**ch**). Это можно сделать разными способами.

- Если позиция чтения доступна, **ch** — это элемент, хранящийся в позиции чтения. Дополнительные сведения об этом см. в разделе "Примечания" для [класса basic_streambuf](../standard-library/basic-streambuf-class.md).

- Можно сделать позицию чтения доступной, выделив новое или дополнительное хранилище для входного буфера, а затем считав из внешнего источника один или несколько элементов. Дополнительные сведения об этом см. в разделе "Примечания" для [класса basic_streambuf](../standard-library/basic-streambuf-class.md).

Если функция не может выполниться успешно, она возвращает `traits_type::`[eof](../standard-library/char-traits-struct.md#eof)`()` или создает исключение. В противном случае она возвращает текущий элемент во входном потоке, преобразованный, как описано выше. По умолчанию возвращается `traits_type::eof()`.

Виртуальная функция `underflow` вместе с функциями [sync](#sync) и [overflow](#overflow) задает характеристики класса, производного от `streambuf`. Каждый производный класс может реализовать `underflow` по-разному, но интерфейс с классом вызывающего потока одинаков.

Функция `underflow` наиболее часто вызывается общими функциями `streambuf`, такими как [sgetc](#sgetc) и [sgetn](#sgetn), когда область get пустая, но другие классы, включая классы потоков, могут вызывать `underflow` в любое время.

Функция `underflow` предоставляет область get с символами из источника входных данных. Если область get содержит символы, `underflow` возвращает первый символ. Если область get пустая, эта функция заполняет область get и возвращает следующий символ (из оставшихся в области get). Если больше нет доступных символов, то `underflow` возвращает `EOF` и оставляет область get пустой.

В классе `strstreambuf` функция `underflow` настраивает указатель [egptr](#egptr) для доступа к хранилищу, которое было выделено динамически путем вызова `overflow`.

## <a name="xsgetn"></a>  basic_streambuf::xsgetn

Защищенная виртуальная функция, которая извлекает элементы из входного потока.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.

```cpp
virtual streamsize xsgetn(
    char_type* ptr,
    streamsize count);
```

### <a name="parameters"></a>Параметры

`ptr` Буфер для хранения извлеченных символов.

`count` Число элементов для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член извлекает до `count` элементов из входного потока, как в результате повторных вызовов [sbumpc](#sbumpc), и сохраняет их в массив начиная с `ptr`. Она возвращает число фактически извлеченных элементов.

## <a name="xsputn"></a>  basic_streambuf::xsputn

Защищенная виртуальная функция, которая вставляет элементы в выходной поток.

```cpp
virtual streamsize xsputn(const char_type* ptr, streamsize count);
```

### <a name="parameters"></a>Параметры

`ptr` Указатель элементов для вставки.

`count` Количество элементов для вставки.

### <a name="return-value"></a>Возвращаемое значение

Число элементов, фактически вставленных в поток.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член вставляет до `count` элементов в выходной поток, как в результате повторных вызовов [sbumpc](#sputc), из массива начиная с `ptr`. Вставка символов в выходной поток останавливается, когда все `count` символов записаны, или в случае вызова `sputc( count)` возвращается `traits::eof()`. Возвращается число фактически вставленных элементов.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>

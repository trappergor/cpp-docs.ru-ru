---
title: Класс time_put
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
ms.openlocfilehash: 10691de0a583dc7d5a66c319968d90978bf59480
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368003"
---
# <a name="time_put-class"></a>Класс time_put

Шаблон класса описывает объект, который может служить в качестве аспекта локализации для `CharType`управления преобразованиями значений времени в последовательности типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов.

*Выводитатор*\
Тип итератора, в который функции записи времени записывают свои выходные данные.

## <a name="remarks"></a>Remarks

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[time_put](#time_put)|Конструктор для объектов типа `time_put`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.|
|[Положить](#put)|Выводит информацию о времени и дате в виде последовательности `CharType`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="time_putchar_type"></a><a name="char_type"></a>time_put::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="time_putdo_put"></a><a name="do_put"></a>time_put::do-put

Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Параметры

*Следующий*\
Итератор вывода, куда необходимо вставить последовательность символов, представляющих дату и время.

*_Iosbase*\
Не используется.

*_pt*\
Выводимые сведения о дате и времени.

*_Fmt*\
Формат вывода См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*_Mod*\
Модификатор для формата. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Remarks

Виртуальная защищенная функция члена генерирует последовательные `next` элементы, начинающиеся \* `_Pt`в час `tm`значений времени, хранящихся в объекте, типа. Функция возвращает итератор, обозначающий следующую позицию для вставки элемента после сформированного вывода.

Выход генерируется теми же `strftime`правилами, используемыми, с последним аргументом *_Pt,* для генерации ряда **элементов char** в массив. Предполагается, что каждый такой **элемент символа** отображается на эквивалентном элементе типа `CharType` простым отображением один на один. Если *_Mod* равняется нулю, то эффективным форматом является "%F", где F заменяется *_Fmt*. В противном случае, эффективный формат "%MF", где M заменяется *_Mod*.

### <a name="example"></a>Пример

См. пример для [put](#put), который вызывает `do_put`.

## <a name="time_putiter_type"></a><a name="iter_type"></a>time_put::iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `OutputIterator`.

## <a name="time_putput"></a><a name="put"></a>time_put::put

Выводит информацию о времени и дате в виде последовательности `CharType`.

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*Следующий*\
Итератор вывода, куда необходимо вставить последовательность символов, представляющих дату и время.

*_Iosbase*\
Не используется.

*_Fill*\
Характер типа, `CharType` используемого для интервала.

*_pt*\
Выводимые сведения о дате и времени.

*_Fmt*\
Формат вывода См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*_Mod*\
Модификатор для формата. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*Первый*\
Начало строки форматирования для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*Последний*\
Конец строки форматирования для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Remarks

Функция первого участника`next` [возвращается do_put](#do_put) `_Mod`(, `_Iosbase`, `_Fill` `_Pt`, , `_Fmt`. . Функция второго члена \* `next` копирует любой элемент `first`в `last`интервале, кроме процента (%). Для процента следуют символ *C* в `first`интервале , `last`, `next`  =  `do_put`функция `next` `_Iosbase`вместо `_Fill` `_Pt`оценки ( , , , *C*, 0) и пропускает мимо *C*. Если, однако, *C* является квалификационным персонажем из набора `C2` EO, `first`а `last`затем символом `next`  =  `do_put`в `next` `_Iosbase`интервале , функция вместо оценки ( , `_Fill`, `_Pt`, `C2`, *C*) и пропускает мимо `C2`.

### <a name="example"></a>Пример

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_puttime_put"></a><a name="time_put"></a>time_put::time_put

Конструктор для объектов типа `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения для *параметра _Refs* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Конструктор инициализирует свой базовый объект с [помощью локализации::facet](../standard-library/locale-class.md#facet_class)*(_Refs).*

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[класс time_base](../standard-library/time-base-class.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

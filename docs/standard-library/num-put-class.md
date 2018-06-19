---
title: Класс num_put | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a860f7c266685e7e10f9b4cbe46c280c356f2681
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862040"
---
# <a name="numput-class"></a>Класс num_put

Шаблонный класс, описывающий объект, который можно использовать как аспект языкового стандарта для управления преобразованиями числовых значений в последовательности типа `CharType`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

`CharType` Тип, используемый внутри программы для кодирования символов в языковом стандарте.

`OutputIterator` Тип итератора, к которому численные функции записывают свои выходные данные.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[num_put](#num_put)|Конструктор для объектов типа `num_put`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, которая вызывается для преобразования числа в последовательность `CharType`, представляющую это число в формате для определенного языкового стандарта.|
|[put](#put)|Преобразует число в последовательность `CharType`, представляющую число в формате для определенного языкового стандарта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="char_type"></a>  num_put::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона **CharType**.

## <a name="do_put"></a>  num_put::do_put

Виртуальная функция, которая вызывается для преобразования числа в последовательность объектов типа **CharType**, которая представляет число в формате заданного языкового стандарта.

```cpp
virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const unsigned long long val) const;
```

### <a name="parameters"></a>Параметры

`next` Итератор, обращающийся к первому элементу вставленной строки.

`_Iosbase` Указанный поток, который содержит языкового стандарта с numpunct аспект, применяемый прерывая выходные данные и флаги для форматирования выходных данных.

`_Fill` Символ, который применяется для интервала.

`val` Номер или логического типа, будут выводиться.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Примечания

Первая виртуальная защищенная функция-член создает последовательные элементы, начиная с `next`, для формирования целочисленного поля вывода из значения `val`. Функция возвращает итератор, обозначающий следующую позицию для вставки элемента после сформированного целочисленного поля вывода.

Целочисленное поле вывода формируется теми же правилами, которые используются функциями печати для выдачи рядов элементов `char` в файл. Предполагается, что каждый такой символьный элемент подбирается к эквивалентному элементу типа **CharType** с помощью простого соответствия "один к одному". Однако в случаях, когда функция печати дополняет поле пробелами или цифрой 0, `do_put` вместо этого использует **fill**. Эквивалентная спецификация преобразования печати определяется следующим образом:

- Если **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[oct](../standard-library/ios-functions.md#oct), спецификация преобразования будет иметь значение **lo**.

- Если **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex), спецификация преобразования будет иметь значение **lx**.

- В противном случае спецификация преобразования будет иметь значение **ld**.

Если **iosbase**. [width](../standard-library/ios-base-class.md#width) не равно нулю, ширина поля этого значения добавляется в начало. Затем функция вызывает **iosbase**. **width**(0) для сброса ширины поля в нуль.

Заполнение происходит, только если минимальное количество элементов *N*, требуемое для указания поля вывода, меньше, чем **iosbase**. [width](../standard-library/ios-base-class.md#width). Такого заполнения состоит из последовательности *N* - **ширина** копий **заполнения**. Заполнение выполняется следующим образом:

- Если **iosbase**. **флаги** & `ios_base::adjustfield` == `ios_base::`[левой](../standard-library/ios-functions.md#left), флаг **-** добавляется. (Заполнение происходит после сформированного текста.)

- Если **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[internal](../standard-library/ios-functions.md#internal), в начало добавляется флаг **0**. (Для числового поля вывода заполнение происходит там, где функции печати заполняют цифрой 0.)

- В противном случае никакие дополнительные флаги в начало не добавляются. (Заполнение происходит перед сформированной последовательностью.)

Как итог:

- Если **iosbase**. **flags** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) не равно нулю, флаг **+** добавляется в начало спецификации преобразования.

- Если **iosbase**. **flags** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) не равно нулю, флаг **#** добавляется в начало спецификации преобразования.

Формат целочисленного поля вывода далее определяется [аспектом языкового стандарта](../standard-library/locale-class.md#facet_class)**fac**, возвращаемым вызовом [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**>(**iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). В частности:

- **fac**. [grouping](../standard-library/numpunct-class.md#grouping) определяет, как будут группироваться цифры слева от любого десятичного разделителя;

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) определяет последовательность, которая разделяет группы цифр слева от любого десятичного разделителя.

Если не накладываются ограничения по группированию со стороны **fac**. **grouping** (первый элемент имеет значение CHAR_MAX), то никакие экземпляры **fac**. `thousands_sep` не будут формироваться в поле вывода. В противном случае после преобразования печати будут вставлены разделители.

Вторая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования **ld** на **lu**.

Третья виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

ведет себя так же, как первая, за исключением того, что она создает поле вывода с плавающей запятой из значения **val**. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) определяет последовательность, которая отделяет цифры целой части от цифр дробной части. Эквивалентная спецификация преобразования печати определяется следующим образом:

- Если **iosbase**. **flags** & `ios_base::floatfield` == `ios_base::`[fixed](../standard-library/ios-functions.md#fixed), спецификация преобразования будет иметь значение **lf**.

- Если **iosbase**. **flags** & **ios_base::floatfield** == `ios_base::`[scientific](../standard-library/ios-functions.md#scientific), спецификация преобразования будет иметь значение `le`. Если **iosbase**. **flags** & `ios_base::`[uppercase](../standard-library/ios-functions.md#uppercase) не равно нулю, **e** заменяется на **E**.

- В противном случае спецификация преобразования будет иметь значение **lg**. Если **iosbase**. **flags** & **ios_base::uppercase** не равно нулю, **g** заменяется на **G**.

Если **iosbase**. **flags** & **ios_base::fixed** не равно нулю или если **iosbase**. [precision](../standard-library/ios-base-class.md#precision) больше нуля, точность со значением **iosbase**. **precision** добавляется в начало спецификации преобразования. Любое заполнение происходит так же, как для целочисленного поля вывода. Символ заполнения — **fill**. Как итог:

- Если **iosbase**. **flags** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) не равно нулю, флаг **+** добавляется в начало спецификации преобразования.

- Если **iosbase**. **flags** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) не равно нулю, в начало спецификации преобразования добавляется флаг **#**.

Четвертая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

ведет себя так же, как первая, за исключением того, что квалификатор **l** в спецификации преобразования заменяется на **L**.

Пятая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

ведет себя так же, как первая, за исключением того, что спецификация преобразования — `p`**,** плюс любые квалификаторы, необходимые для указания заполнения.

Шестая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

ведет себя так же, как первая, за исключением того, что она формирует из `val` логическое поле вывода.

Логическое поле вывода принимает одну из двух форм. Если **iosbase**. **flags** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) имеет значение **false**, функция-член возвращает `do_put`(_ *Next*, \_ *Iosbase*, \_ *Fill*, (**long**) `val`), что обычно формирует созданную последовательность из 0 (для значения **false**) или 1 (для значения **true**). В противном случае сформированная последовательность либо **fac**. [falsename](../standard-library/numpunct-class.md#falsename)`)` (для значения **false**), либо **fac**. [truename](../standard-library/numpunct-class.md#truename) (для значения **true**).

Седьмая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования **ld** на **lld**.

Восьмая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `llu`.

### <a name="example"></a>Пример

См. пример для [put](#put), который вызывает `do_put`.

## <a name="iter_type"></a>  num_put::iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона **OutputIterator.**

## <a name="num_put"></a>  num_put::num_put

Конструктор для объектов типа `num_put`.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

`_Refs` Целочисленное значение используется для указания типа управление памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения параметра `_Refs` и их важность:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \> 1: эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект через **locale::**[facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="put"></a>  num_put::put

Преобразует число в последовательность объектов типа **CharType**, которая представляет число в формате заданного языкового стандарта.

```cpp
iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Unsigned long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;
```

### <a name="parameters"></a>Параметры

`dest` Итератор, обращающийся к первому элементу вставленной строки.

`_Iosbase` Указанный поток, содержащий языкового стандарта с аспектом numpunct используется прерывая выходные данные и флаги для форматирования выходных данных.

`_Fill` Символ, который применяется для интервала.

`val` Номер или логического типа, будут выводиться.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Примечания

Все функции-члены возвращают [do_put](#do_put)(`next`, `_Iosbase`, `_Fill`, `val`).

### <a name="example"></a>Пример

```cpp
// num_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );
   basic_stringstream<char> psz2;
   ios_base::iostate st = 0;
   long double fVal;
   cout << "The thousands separator is: "
        << use_facet < numpunct <char> >(loc).thousands_sep( )
        << endl;

   psz2.imbue( loc );
   use_facet < num_put < char > >
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),
                    psz2, ' ', fVal=1000.67);

   if ( st & ios_base::failbit )
      cout << "num_put( ) FAILED" << endl;
   else
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;
}
```

```Output
The thousands separator is: .
num_put( ) = 1.000,67
```

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)<br/>
[Класс Facet](../standard-library/locale-class.md#facet_class)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

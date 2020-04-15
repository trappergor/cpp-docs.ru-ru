---
title: Класс num_put
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
ms.openlocfilehash: 3f65d7140bb5c691fa58ec9d74ceda5573280ddb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373649"
---
# <a name="num_put-class"></a>Класс num_put

Шаблон класса, описывающий объект, который может служить в качестве аспекта локаль для `CharType`управления преобразованиями числовых значений в последовательности типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

*Выводитатор*\
Тип итератора, куда численные функции записывают свои выходные данные.

## <a name="remarks"></a>Remarks

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

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, которая вызывается для преобразования числа в последовательность `CharType`, представляющую это число в формате для определенного языкового стандарта.|
|[Положить](#put)|Преобразует число в последовательность `CharType`, представляющую число в формате для определенного языкового стандарта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="num_putchar_type"></a><a name="char_type"></a>num_put::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="num_putdo_put"></a><a name="do_put"></a>num_put::do-put

Виртуальная функция, которая вызывается для преобразования числа в последовательность `CharType`, представляющую это число в формате для определенного языкового стандарта.

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

*Следующий*\
Итератор, адресующий первый элемент во вставляемой строке.

*_Iosbase*\
Указывает поток, который содержит языковой стандарт с аспектом numpunct, используемым для расстановки знаков препинания в выводе, и флагами для форматирования вывода.

*_Fill*\
Символ, используемый для расстановки интервалов.

*Валь*\
Числовой или логический тип для возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Remarks

Первая виртуальная защищенная функция члена генерирует последовательные элементы, начиная *с следующего,* чтобы произвести рядовое поле вывода от значения *val*. Функция возвращает итератор, обозначающий следующую позицию для вставки элемента после сформированного целочисленного поля вывода.

Поле вывода спешки генерируется теми же правилами, которые используются функциями печати для генерации ряда **элементов char** в файле. Предполагается, что каждый такой элемент символа отображается на эквивалентном элементе типа `CharType` простым отображением один на один. Однако там, где функция печати прокладывает поле `do_put` с `fill`пробелами или цифрой 0, вместо этого используется. Эквивалентная спецификация преобразования печати определяется следующим образом:

- Если **iosbase**. [флаги](../standard-library/ios-base-class.md#flags) & `ios_base::`[oct](../standard-library/ios-functions.md#oct) `lo`октября , спецификация преобразования .`ios_base::basefield` == 

- Если **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex), `lx`спецификация преобразования .

- В противном случае спецификация преобразования имеет значение `ld`.

Если **iosbase**. [width](../standard-library/ios-base-class.md#width) не равно нулю, ширина поля этого значения добавляется в начало. Затем функция вызывает **iosbase**. **width**(0) для сброса ширины поля в нуль.

Заполнение происходит, только если минимальное количество элементов *N*, требуемое для указания поля вывода, меньше, чем **iosbase**. [ширина](../standard-library/ios-base-class.md#width). Такая обивка состоит из последовательности *N* - **ширины** копии **заполнения**. Заполнение выполняется следующим образом:

- Если **iosbase**. **флаги** & `ios_base::`[left](../standard-library/ios-functions.md#left) **-** слева, флаг заранее.`ios_base::adjustfield` ==  (Заполнение происходит после сформированного текста.)

- Если **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[внутреннее,](../standard-library/ios-functions.md#internal)флаг **0** prepended. (Для числового поля вывода заполнение происходит там, где функции печати заполняют цифрой 0.)

- В противном случае никакие дополнительные флаги в начало не добавляются. (Заполнение происходит перед сформированной последовательностью.)

Как итог:

- Если **iosbase**. **флаги** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) незеро, флаг **+** готовится к спецификации преобразования.

- Если **iosbase**. **флаги** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) является **#** ненулевой, флаг готовится к спецификации преобразования.

Формат целочисленного поля вывода далее определяется [аспектом языкового стандарта](../standard-library/locale-class.md#facet_class)**fac**, возвращаемым вызовом [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**>(**iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). В частности:

- **fac**. [группировка](../standard-library/numpunct-class.md#grouping) определяет, как цифры группируются слева от любой десятичной точки

- **fac**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep) определяет последовательность, которая разделяет группы цифр слева от любого десятичного разделителя.

Если не накладываются ограничения по группированию со стороны **fac**. **grouping** (первый элемент имеет значение CHAR_MAX), то никакие экземпляры **fac**. `thousands_sep` не будут формироваться в поле вывода. В противном случае после преобразования печати будут вставлены разделители.

Вторая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `lu`.

Третья виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

ведет себя так же, как первая, за исключением того, что она создает поле вывода с плавающей запятой из значения **val**. **fac**. [decimal_point](../standard-library/numpunct-class.md#decimal_point) определяет последовательность, которая отделяет цифры целой части от цифр дробной части. Эквивалентная спецификация преобразования печати определяется следующим образом:

- Если **iosbase**. **флаги** & `ios_base::`[fixed](../standard-library/ios-functions.md#fixed) `lf`фиксированной, спецификации преобразования .`ios_base::floatfield` == 

- Если **iosbase**. **флаги** & **ios_base::floatfield** == `ios_base::`[научных](../standard-library/ios-functions.md#scientific), `le`конверсия спецификации . Если **iosbase**. **флаги** & `ios_base::`[верхний](../standard-library/ios-functions.md#uppercase) регистр `e` ненулевой, заменяется `E`.

- В противном случае спецификация преобразования будет иметь значение **lg**. Если **iosbase**. **флаги** & **ios_base:::uppercase** `g` является ненулевой, заменяется `G`.

Если **iosbase**. **флаги** & **ios_base::фиксированный** является ненулевым или если **iosbase**. [precision](../standard-library/ios-base-class.md#precision) больше нуля, точность со значением **iosbase**. **precision** добавляется в начало спецификации преобразования. Любое заполнение происходит так же, как для целочисленного поля вывода. Символ заполнения — **fill**. Как итог:

- Если **iosbase**. **флаги** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) незеро, флаг **+** готовится к спецификации преобразования.

- Если **iosbase**. **флаги** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) незеро, флаг **#** готовится к спецификации преобразования.

Четвертая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

ведет себя так же третий, `l` за исключением того, `L`что квалификатор в спецификации преобразования заменяется .

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

ведет себя так же, как первый, за исключением того, что он генерирует поле выхода Boolean из *val*.

Логическое поле вывода принимает одну из двух форм. Если `iosbase.flags & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) **является ложным,** `do_put(_Next, _Iosbase, _Fill, (long)val)`функция члена возвращается, который обычно производит сгенерированную последовательность либо 0 (для **ложных)** или 1 **(правда).** В противном случае, сгенерированная последовательность либо *fac*. [ложное имя](../standard-library/numpunct-class.md#falsename) (для **ложных**), или *fac*. [истинное имя](../standard-library/numpunct-class.md#truename) (для **истинного**).

Седьмая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `lld`.

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

## <a name="num_putiter_type"></a><a name="iter_type"></a>num_put:::iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом параметра-шаблона **OutputIterator.**

## <a name="num_putnum_put"></a><a name="num_put"></a>num_put::num_put

Конструктор для объектов типа `num_put`.

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения для *параметра _Refs* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект через **locale::**[facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="num_putput"></a><a name="put"></a>num_put::p

Преобразует число в последовательность `CharType`s, которая представляет число, отформатированный для данного локализов.

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

*Dest*\
Итератор, адресующий первый элемент во вставляемой строке.

*_Iosbase*\
Указывает поток, который содержит языковой стандарт с аспектом numpunct, используемым для расстановки знаков препинания вывода и флагами для форматирования вывода.

*_Fill*\
Символ, используемый для расстановки интервалов.

*Валь*\
Числовой или логический тип для возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Remarks

Все функции участника `_Iosbase`возвращают `_Fill` `val` [do_put](#do_put)(, `next`, , ).

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

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[класс граней](../standard-library/locale-class.md#facet_class)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

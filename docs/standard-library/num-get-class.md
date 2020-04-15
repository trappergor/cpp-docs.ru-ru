---
title: Класс num_get
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
ms.openlocfilehash: 76d2832141c65ca67c42f1994a3c8f5b532f0092
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373659"
---
# <a name="num_get-class"></a>Класс num_get

Шаблон класса, описывающий объект, который может служить в качестве аспекта `CharType` локаль для управления преобразованиями последовательностей типа в числовые значения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

*Inputiterator*\
Тип итератора, из которого функции получения числовых значений считывают своих входные данные.

## <a name="remarks"></a>Remarks

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[num_get](#num_get)|Конструктор для объектов типа `num_get`, используемых для извлечения числовых значений из последовательностей.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор ввода.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_get](#do_get)|Виртуальная функция, вызываемая для извлечения числового или логического значения из последовательности символов, представляющей денежное значение.|
|[get](#get)|Извлекает числовое или логическое значение из последовательности символов.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="num_getchar_type"></a><a name="char_type"></a>num_get::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом для параметра-шаблона **Chartype**.

## <a name="num_getdo_get"></a><a name="do_get"></a>num_get::do-get

Виртуальная функция, вызываемая для извлечения числового или логического значения из последовательности символов, представляющей денежное значение.

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

### <a name="parameters"></a>Параметры

*Первый*\
Начало диапазона символов для чтения числа.

*Последний*\
Конец диапазона символов для чтения числа.

*iosbase*\
[Ios_base](../standard-library/ios-base-class.md), флаги которого используются для преобразования.

*Государства*\
Состояние, к которому при сбое добавляется failbit (см. [ios_base::iostate](../standard-library/ios-base-class.md#iostate)).

*Валь*\
Прочитанное значение.

### <a name="return-value"></a>Возвращаемое значение

Итератор после чтения значения.

### <a name="remarks"></a>Remarks

Первая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;
```

соответствует последовательным элементам, начинающимся *сначала* в последовательности, `[first, last)` пока не распознает полное, непустое поле ввода. В случае успеха, он преобразует это поле в эквивалентное значение в качестве типа **долго,** и сохраняет результат в *валь*. Она возвращает итератор, обозначающий первый элемент после числового поля ввода. В противном случае, *val* функция `ios_base::failbit` ничего не хранит в Валь и устанавливает в `state`. Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого целочисленного поля ввода. В любом случае, если возвращаемое значение равно `last`, функция устанавливает `ios_base::eofbit` в `state`.

Поле ввода integer преобразуется теми же правилами, которые используются функциями сканирования для сопоставления и преобразования ряда **элементов char** из файла. (Каждый такой **элемент символа** предполагается сопоставить с эквивалентным элементом типа `Elem` простым, один к одному, отображение.) Эквивалентная спецификация преобразования сканирования определяется следующим образом:

Если `iosbase.` [ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[oct,](../standard-library/ios-functions.md#oct)спецификация преобразования . `lo`

Если `iosbase.flags() & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex), спецификация преобразования имеет значение `lx`.

Если `iosbase.flags() & ios_base::basefield == 0`, спецификация преобразования имеет значение `li`.

В противном случае спецификация преобразования имеет значение `ld`.

Формат входной поля рядом определяется [логово логосов,](../standard-library/locale-class.md#facet_class) `fac` возвращенное вызовом [use_facet](../standard-library/locale-functions.md#use_facet) `<` [numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.`[ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())`. В частности:

`fac.`[numpunct::grouping](../standard-library/numpunct-class.md#grouping) `()` определяет, как цифры сгруппированы слева от любой десятичной точки

`fac.`[numpunct::thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` определяет последовательность, которая отделяет группы цифр слева от любой десятичной точки.

Если в числовом поле ввода нет экземпляров `fac.thousands_sep()`, то ограничения группировки не применяются. В противном случае применяются ограничения группировки, накладываемые `fac.grouping()`, и разделители удаляются перед выполнением преобразования сканирования.

Четвертая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `lu`. В случае успеха он преобразует числовое поле ввода в значение типа **неподписанных долго** и хранит, что значение в *валь*.

Пятая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `lld`. В случае успеха он преобразует числовой входиного поля в значение типа **долго** и хранит, что значение в *валь*.

Шестая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `llu`. В случае успеха он преобразует числовое вхотворное поле в значение типа **неподписанных долго** и хранит, что значение в *валь*.

Седьмая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

ведет себя так же, как первая, за исключением того, что она пытается сопоставить полное, непустое вещественное поле ввода. `fac.`[numpunct::decimal'point](../standard-library/numpunct-class.md#decimal_point) `()` определяет последовательность, отделяет целые цифры от цифр фракции. Эквивалентный спецификатор преобразования сканирования — `lf`.

Восьмая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

ведет себя так же, как первая, за исключением того, что она пытается сопоставить полное, непустое вещественное поле ввода. `fac.`[numpunct::decimal'point](../standard-library/numpunct-class.md#decimal_point) `()` определяет последовательность, отделяет целые цифры от цифр фракции. Эквивалентный спецификатор преобразования сканирования — `lf`.

Девятая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

ведет себя так же, как восьмая, за исключением того, что эквивалентный спецификатор преобразования сканирования — `Lf`.

Десятая виртуальная защищенная функция члена:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

ведет себя так же, как первая, за исключением того, что эквивалентный спецификатор преобразования сканирования — `p`.

Последняя (одиннадцатая) виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

ведет себя так же, как первая, за исключением того, что она пытается сопоставить полное, непустое логическое поле ввода. В случае успеха он преобразует поле ввода Boolean в значение типа **bool** и хранит, что значение в *валь*.

Логическое поле ввода может иметь одну из двух форм. Если `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) имеет значение false, поле совпадает с целочисленным полем ввода, за исключением того, что преобразованное значение должно быть 0 (false) или 1 (true). В противном случае, `fac.`последовательность должна соответствовать либо [numpunct::falsename](../standard-library/numpunct-class.md#falsename) `()` (для `fac.` [ложных), или numpunct::truename](../standard-library/numpunct-class.md#truename) `()` (правда).

### <a name="example"></a>Пример

См. пример для [get](#get), где виртуальная функция-член вызывается из `do_get`.

## <a name="num_getget"></a><a name="get"></a>num_get::get

Извлекает числовое или логическое значение из последовательности символов.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

### <a name="parameters"></a>Параметры

*Первый*\
Начало диапазона символов для чтения числа.

*Последний*\
Конец диапазона символов для чтения числа.

*iosbase*\
[Ios_base](../standard-library/ios-base-class.md), флаги которого используются для преобразования.

*Государства*\
Состояние, к которому при сбое добавляется failbit (см. [ios_base::iostate](../standard-library/ios-base-class.md#iostate)).

*Валь*\
Прочитанное значение.

### <a name="return-value"></a>Возвращаемое значение

Итератор после чтения значения.

### <a name="remarks"></a>Remarks

Все функции члена возвращают [do_get](#do_get)`( first, last, iosbase, state, val)`.

Первая защищенная виртуальная функция-член пытается сопоставить последовательные элементы, начиная с первого в последовательности [`first`, `last`), пока не распознает полное, непустое целочисленное поле ввода. В случае успеха, он преобразует это поле в эквивалентное значение в качестве типа **долго** и хранит результат в *валь*. Она возвращает итератор, обозначающий первый элемент после числового поля ввода. В противном случае функция ничего не хранит в *валь* и устанавливает `ios_base::failbit` в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого целочисленного поля ввода. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

Поле ввода integer преобразуется теми же правилами, которые используются функциями сканирования для сопоставления и преобразования ряда **элементов char** из файла. Предполагается, что каждый такой **элемент символа** отображается на эквивалентном элементе типа `CharType` простым отображением один на один. Эквивалентная спецификация преобразования сканирования определяется следующим образом:

- Если `iosbase.` [флаги](../standard-library/ios-base-class.md#flags)`& ios_base::basefield == ios_base::`[октября,](../standard-library/ios-functions.md#oct) `lo`конверсия спецификации .

- Если `iosbase.flags & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex), спецификация преобразования имеет значение `lx`.

- Если `iosbase.flags & ios_base::basefield == 0`, спецификация преобразования имеет значение `li`.

- В противном случае спецификация преобразования имеет значение `ld`.

Формат входной поля несколько разов, определяемый [логово](../standard-library/locale-class.md#facet_class) `fac` локаля, возвращенное вызовом [use_facet](../standard-library/locale-functions.md#use_facet)`<`[`numpunct`](../standard-library/numpunct-class.md)`<Elem>(iosbase.`[getloc.](../standard-library/ios-base-class.md#getloc)`())` В частности:

- `fac.`[группировка](../standard-library/numpunct-class.md#grouping) определяет, как цифры группируются слева от любой десятичной точки.

- `fac.`[thousands_sep](../standard-library/numpunct-class.md#thousands_sep) определяет последовательность, отделяет группы цифр слева от любой десятичной точки.

Если в числовом поле ввода нет экземпляров `fac.thousands_sep`, то ограничения группировки не применяются. В противном случае любые ограничения группировки, налагаемые `fac.grouping` на них, применяются, и сепараторы удаляются до того, как произойдет преобразование сканирования.

Вторая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

ведет себя так же, как первая, за исключением того, что она заменяет спецификацию преобразования `ld` на `lu`. В случае успеха, он преобразует числовой входиного поля в значение типа **неподписанных долго** и хранит, что значение в *валь*.

Третья виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

ведет себя так же, как первая, за исключением того, что она пытается сопоставить полное, непустое вещественное поле ввода. `fac.`[decimal_point](../standard-library/numpunct-class.md#decimal_point) определяет последовательность, отделяет целые цифры от цифр фракции. Эквивалентный спецификатор преобразования сканирования — `lf`.

Четвертая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

ведет себя так же третий, за исключением того, `Lf`что эквивалентный спецификация преобразования сканирования .

Пятая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

ведет себя так же, как первая, за исключением того, что эквивалентный спецификатор преобразования сканирования — `p`.

Шестая виртуальная защищенная функция-член:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

ведет себя так же, как первая, за исключением того, что она пытается сопоставить полное, непустое логическое поле ввода. В случае успеха он преобразует поле ввода Boolean в значение типа **bool** и хранит, что значение в *валь*.

Логическое поле ввода может иметь одну из двух форм. Если `iosbase.flags & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) **является ложным,** это то же самое, как целый входполе поле, за исключением того, что преобразованное значение должно быть либо 0 (для **ложных**) или 1 (для **истинного**). В противном случае, `fac.`последовательность должна соответствовать либо [ложное имя](../standard-library/numpunct-class.md#falsename) (для **ложных**), или `fac.` [truename](../standard-library/numpunct-class.md#truename) **(правда**).

### <a name="example"></a>Пример

```cpp
// num_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   basic_stringstream<char> psz, psz2;
   psz << "-1000,56";

   ios_base::iostate st = 0;
   long double fVal;
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;

   psz.imbue( loc );
   use_facet <num_get <char> >
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter(0), psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get( ) FAILED" << endl;
   else
      cout << "money_get( ) = " << fVal << endl;
}
```

## <a name="num_getiter_type"></a><a name="iter_type"></a>num_get::iter_type

Тип, который описывает итератор ввода.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `InputIterator`.

## <a name="num_getnum_get"></a><a name="num_get"></a>num_get:::num_get

Конструктор для объектов типа `num_get`, используемых для извлечения числовых значений из последовательностей.

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>Параметры

*Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения параметра *рефери* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой `locale::`базовый объект`(refs)` [граней.](../standard-library/locale-class.md#facet_class)

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[класс граней](../standard-library/locale-class.md#facet_class)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

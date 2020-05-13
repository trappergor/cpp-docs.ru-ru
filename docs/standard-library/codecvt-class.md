---
title: Класс codecvt
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 3dba971b112c23325e0529e53746cbee827df5e9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371951"
---
# <a name="codecvt-class"></a>Класс codecvt

Шаблон класса, описывающий объект, который может служить в качестве аспекта языка. Он может управлять преобразованиями между последовательностями значений, используемых для кодирования символов внутри программы, и последовательностями значений, используемых для кодирования символы вне программы.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов.

*Байт*\
Тип, используемый для кодирования символов вне программы.

*StateType*\
Тип, который можно использовать для представления промежуточных состояний преобразования между внутренними и внешними типами представлений символов.

## <a name="remarks"></a>Remarks

Шаблон класса описывает объект, который может служить в качестве [аспекта локализации,](../standard-library/locale-class.md#facet_class)для управления преобразованиями между последовательностью значений типа *CharType* и последовательностью значений типа *Byte.* Класс *StateType* характеризует преобразование - и объект класса *StateType* хранит любую необходимую государственную информацию во время преобразования.

Внутреннее кодирование использует представление с фиксированным числом байтов на символ, как правило, либо типа **символ** или тип **wchar_t.**

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического `id` объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`.

Шаблонные версии [do_in](#do_in) и [do_out](#do_out) всегда возвращают `codecvt_base::noconv`.

Стандартная библиотека C++ определяет несколько явных специализаций:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

преобразуетмежду **wchar_t** и **символами** последовательности.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

преобразуется `char16_t` между последовательностями, кодируемыми как UTF-16, и **символными** последовательностями, кодируемыми как UTF-8.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

преобразуется `char32_t` между последовательностями, кодируемыми как UTF-32 (UCS-4) и **символом** последовательности, кодируемые как UTF-8.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[codecvt](#codecvt)|Конструктор для объектов класса `codecvt`, который служит в качестве аспекта языкового стандарта для обработки преобразований.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[extern_type](#extern_type)|Тип символа, используемый для внешних представлений.|
|[intern_type](#intern_type)|Тип символа, используемый для внутренних представлений.|
|[state_type](#state_type)|Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[always_noconv](#always_noconv)|Проверяет, не требуется ли выполнит преобразования.|
|[do_always_noconv](#do_always_noconv)|Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.|
|[do_encoding](#do_encoding)|Виртуальная функция, которая проверяет, зависит `Byte` ли кодирование потока, зависит `Byte` от состояния, `CharType` является ли соотношение между используемыми значениями и производимыми значениями постоянным, и если да, то определяет значение этого соотношения.|
|[do_in](#do_in)|Виртуальная функция, призванная преобразовать последовательность внутренних `Byte` значений в последовательность внешних `CharType` значений.|
|[do_length](#do_length)|Виртуальная функция, которая `Byte` определяет, сколько значений `Byte` из заданной последовательности внешних значений производит не более определенного количества внутренних `CharType` значений и возвращает это количество значений. `Byte`|
|[do_max_length](#do_max_length)|Виртуальная функция, возвращающая максимальное число внешних байтов, необходимых для создания одного внутреннего `CharType`.|
|[do_out](#do_out)|Виртуальная функция, призванная преобразовать последовательность внутренних `CharType` значений в последовательность внешних байтов.|
|[do_unshift](#do_unshift)|Виртуальная функция, называемая для обеспечения `Byte` значений, необходимых в преобразовании, зависям от состояния, для завершения последнего символа в последовательности значений. `Byte`|
|[encoding](#encoding)|Тесты, зависит ли кодирование `Byte` потока от состояния, является `Byte` ли соотношение `CharType` между используемыми значениями и производимыми значениями постоянным, и если да, то определяетзначение этого соотношения.|
|[in](#in)|Преобразует внешнее представление последовательности `Byte` значений во внутреннее представление `CharType` последовательности значений.|
|[длина](#length)|Определяет, сколько `Byte` значений из заданной `Byte` последовательности внешних значений производит `CharType` не более определенного `Byte` количества внутренних значений и возвращает это количество значений.|
|[max_length](#max_length)|Возвращает максимальное количество `Byte` внешних значений, `CharType`необходимых для создания одного внутреннего.|
|[из](#out)|Преобразует последовательность внутренних `CharType` значений в `Byte` последовательность внешних значений.|
|[unshift](#unshift)|Обеспечивает внешние `Byte` значения, необходимые в преобразовании, зависям от `Byte` состояния, для завершения последнего символа в последовательности значений.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a>codecvt::always_noconv

Тестирует, нужно ли делать преобразования.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение Boolean, которое **верно,** если не требуется преобразований; **ложно,** если хотя бы один должен быть сделан.

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_always_noconv](#do_always_noconv).

### <a name="example"></a>Пример

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a>codecvt:codecvt

Конструктор для объектов класса codecvt, который служит в качестве аспекта языкового стандарта для обработки преобразований.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>Параметры

*Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения параметра *рефери* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- 2: Эти значения не определены.

Конструктор инициализирует свой `locale::facet` базовый объект с [помощью локализации::facet](../standard-library/locale-class.md#facet_class)`(refs)`.

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a>codecvt::do'always'noconv

Виртуальная функция, вызванная для проверки необходимости в конверсиях.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная функция виртуального члена возвращается **верно** только `noconv`в том случае, если каждый звонок [do_in](#do_in) или [do_out](#do_out) возвращается.

Версия шаблона всегда возвращает **true**.

### <a name="example"></a>Пример

См. пример для [always_noconv](#always_noconv), в котором вызывается `do_always_noconv`.

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a>codecvt::do-encoding

Виртуальная функция, которая проверяет, зависит `Byte` ли кодирование потока, зависит `Byte` от состояния, `CharType` является ли соотношение между используемыми значениями и производимыми значениями постоянным и, если да, то определяет значение этого соотношения.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная функция-член возвращает:

- -1, если кодирование последовательностей типа `extern_type` зависит от состояния.

- 0, если кодировка включает последовательности переменной длины;

- *N*, если кодирование включает в себя только последовательности длины *N*

### <a name="example"></a>Пример

См. пример для [encoding](#encoding), в котором вызывается `do_encoding`.

## <a name="codecvtdo_in"></a><a name="do_in"></a>codecvt::do'in

Виртуальная функция, призванная преобразовать последовательность `Byte` внешних `CharType` значений в последовательность внутренних значений.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Указатель за пределами преобразованной последовательности для первого непреобразованного символа.

*first2*\
Указатель на начало преобразованной последовательности.

*последний2*\
Указатель на конец преобразованной последовательности.

*next2*\
Указатель на `CharType` то, что `CharType`происходит после последнего преобразованы , к первому неизменному символу в последовательности назначения.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:

- `codecvt_base::error`если исходная последовательность плохо сформирована.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`если преобразование преуспевает.

- `codecvt_base::partial`если источник недостаточен или если назначение не достаточно большо, для преобразования преуспеть.

### <a name="remarks"></a>Remarks

*состояние* должно представлять исходное состояние преобразования в начале новой последовательности исходных источников. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.

### <a name="example"></a>Пример

См. пример для [in](#in), в котором вызывается `do_in`.

## <a name="codecvtdo_length"></a><a name="do_length"></a>codecvt::do'длина

Виртуальная функция, которая `Byte` определяет, сколько значений `Byte` из заданной последовательности внешних значений производит не более определенного количества внутренних `CharType` значений и возвращает это количество значений. `Byte`

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало внешней последовательности.

*last1*\
Указатель на конец внешней последовательности.

*len2*\
Максимальное количество `Byte` значений, которые могут быть возвращены функцией участника.

### <a name="return-value"></a>Возвращаемое значение

Целый ряд, который представляет собой количество максимального числа конверсий, не больше, `first1`чем `last1` *len2*, определяется внешней последовательности источника на й , .

### <a name="remarks"></a>Remarks

Защищенная функция виртуального `do_in( state, first1, last1, next1, buf, buf + len2, next2)` члена эффективно требует *состояния* (копия состояния), `next1` `next2`некоторого буфера, `buf`указателей и .

Затем он `next2`  -  `buf`возвращается . Таким образом, он подсчитывает максимальное количество конверсий, не `first1` `last1`больше, чем *len2*, определяется последовательностью источника на й , .

Шаблон версия всегда возвращает меньшее *из last1* - *first1* и *len2*.

### <a name="example"></a>Пример

Смотрите пример [длины,](#length) `do_length`который вызывает .

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a>codecvt::do'max'length

Виртуальная функция, которая возвращает `Byte` максимальное количество внешних `CharType`значений, необходимых для создания одного внутреннего.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество `Byte` значений, необходимых для производства одного. `CharType`

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена возвращает самое большое допустимое значение, которое может быть возвращено [do_length](#do_length) `( first1, last1, 1)` для произвольных действительных значений *first1* и *last1*.

### <a name="example"></a>Пример

См. пример для [max_length](#max_length), в котором вызывается `do_max_length`.

## <a name="codecvtdo_out"></a><a name="do_out"></a>codecvt::do

Виртуальная функция, призванная преобразовать последовательность внутренних `CharType` значений в последовательность внешних `Byte` значений.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Ссылка на указатель на `CharType`первый непреобразованный, после последнего `CharType` преобразованы.

*first2*\
Указатель на начало преобразованной последовательности.

*последний2*\
Указатель на конец преобразованной последовательности.

*next2*\
Ссылка на указатель на `Byte`первый непреобразованный, после последнего `Byte` преобразованы.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`если исходная последовательность плохо сформирована.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`если преобразование преуспевает.

- `codecvt_base::partial`если источник недостаточен или если пункт назначения не достаточно большой для преобразования для того чтобы преуспеть.

### <a name="remarks"></a>Remarks

*состояние* должно представлять исходное состояние преобразования в начале новой последовательности исходных источников. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.

### <a name="example"></a>Пример

См. пример для [out](#out), в котором вызывается `do_out`.

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a>codecvt::do'unshift

Виртуальная функция, называемая для обеспечения `Byte` значений, необходимых в преобразовании, зависям от состояния, для завершения последнего символа в последовательности значений. `Byte`

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first2*\
Указатель первой позиции в целевом диапазоне.

*последний2*\
Указатель последней позиции в целевом диапазоне.

*next2*\
Указатель на первый неизмененный элемент в целевой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`если *состояние* представляет недействительное состояние

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`если преобразование преуспевает

- `codecvt_base::partial`если пункт назначения не является достаточно большим для преобразования, чтобы преуспеть

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена пытается `CharType`преобразовать исходный элемент (0) `last2`в последовательность назначения, `Byte`которую он хранит в пределах й, `first2`, за исключением элемента прекращения (0). Он всегда хранит в *next2* указатель на первый неизмененный элемент в последовательности назначения.

Объект _ *State* должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Обычно преобразование исходного элемента `CharType`(0) оставляет текущее состояние в исходном состоянии преобразования.

### <a name="example"></a>Пример

См. пример для [unshift](#unshift), в котором вызывается `do_unshift`.

## <a name="codecvtencoding"></a><a name="encoding"></a>codecvt::кодирование

Тесты, зависит ли кодирование `Byte` потока от состояния, является `Byte` ли соотношение `CharType` между используемыми значениями и производимыми значениями постоянным, и если да, то определяетзначение этого соотношения.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если значение возврата положительное, то это `Byte` значение — это `CharType` постоянное количество символов, необходимых для создания персонажа.

Защищенная функция-член возвращает:

- -1, если кодирование последовательностей типа `extern_type` зависит от состояния.

- 0, если кодировка включает последовательности переменной длины;

- *N*, если кодировка включает только последовательности длиной *N*.

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_encoding](#do_encoding).

### <a name="example"></a>Пример

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a>codecvt::extern_type

Тип символа, используемый для внешних представлений.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `Byte`.

## <a name="codecvtin"></a><a name="in"></a>codecvt::in

Преобразует внешнее представление последовательности `Byte` значений во внутреннее представление `CharType` последовательности значений.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Указатель за пределами преобразованной последовательности для первого непреобразованного символа.

*first2*\
Указатель на начало преобразованной последовательности.

*последний2*\
Указатель на конец преобразованной последовательности.

*next2*\
Указатель на `CharType` то, что `Chartype` происходит после последнего преобразуется в первый неизмененный символ в последовательности назначения.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:

- `codecvt_base::error`если исходная последовательность плохо сформирована.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`если преобразование преуспевает.

- `codecvt_base::partial`если источник недостаточен или если пункт назначения не достаточно большой для преобразования для того чтобы преуспеть.

### <a name="remarks"></a>Remarks

*состояние* должно представлять исходное состояние преобразования в начале новой последовательности исходных источников. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. После частичного преобразования необходимо установить *состояние,* чтобы позволить преобразованию возобновиться по прибытии новых символов.

Функция участника [возвращается do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`.

### <a name="example"></a>Пример

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a>codecvt::intern_type

Тип символа, используемый для внутренних представлений.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="codecvtlength"></a><a name="length"></a>codecvt::длина

Определяет, сколько `Byte` значений из заданной `Byte` последовательности внешних значений производит `CharType` не более определенного `Byte` количества внутренних значений и возвращает это количество значений.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало внешней последовательности.

*last1*\
Указатель на конец внешней последовательности.

*len2*\
Максимальное число объектов Byte, которое может возвратить функция-член.

### <a name="return-value"></a>Возвращаемое значение

Целый ряд, который представляет собой количество максимального числа конверсий, не больше, `first1`чем `last1` *len2*, определяется внешней последовательности источника на й , .

### <a name="remarks"></a>Remarks

Функция участника [возвращается do_length](#do_length)`( state, first1, last1, len2)`.

### <a name="example"></a>Пример

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a>codecvt::max_length

Возвращает максимальное количество `Byte` внешних значений, `CharType`необходимых для создания одного внутреннего.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество `Byte` значений, необходимых для производства одного. `CharType`

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_max_length](#do_max_length).

### <a name="example"></a>Пример

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a>codecvt::out

Преобразует последовательность внутренних `CharType` значений в `Byte` последовательность внешних значений.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Ссылка на указатель на `CharType` первый `CharType` непреобразованный после последнего преобразованного.

*first2*\
Указатель на начало преобразованной последовательности.

*последний2*\
Указатель на конец преобразованной последовательности.

*next2*\
Ссылка на указатель на `Byte` первый непреобразованный после последнего преобразованного. `Byte`

### <a name="return-value"></a>Возвращаемое значение

Функция участника [возвращается do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в описании [codecvt::do_out](#do_out).

### <a name="example"></a>Пример

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a>codecvt::state_type

Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для параметра шаблона `StateType`.

## <a name="codecvtunshift"></a><a name="unshift"></a>codecvt::unshift

Обеспечивает `Byte` значения, необходимые в преобразовании, зависям от `Byte` состояния, для завершения последнего символа в последовательности значений.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*Государства*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first2*\
Указатель первой позиции в целевом диапазоне.

*последний2*\
Указатель последней позиции в целевом диапазоне.

*next2*\
Указатель на первый неизмененный элемент в целевой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`если состояние представляет собой недействительное состояние.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`если преобразование преуспевает.

- `codecvt_base::partial`если пункт назначения не достаточно велик для преобразования, чтобы преуспеть.

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена пытается `CharType`преобразовать исходный элемент (0) `last2`в последовательность назначения, `Byte`которую он хранит в пределах й, `first2`, за исключением элемента прекращения (0). Он всегда хранит в *next2* указатель на первый неизмененный элемент в последовательности назначения.

*состояние* должно представлять исходное состояние преобразования в начале новой последовательности исходных источников. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Обычно преобразование исходного элемента `CharType`(0) оставляет текущее состояние в исходном состоянии преобразования.

Функция участника [возвращается do_unshift](#do_unshift)`( state, first2, last2, next2 )`.

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[Страницы кода](../c-runtime-library/code-pages.md)\
[Названия языков, языков и страновых/регионов](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

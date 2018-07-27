---
title: Класс ctype | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::ctype
- xlocale/std::ctype::char_type
- xlocale/std::ctype::do_is
- xlocale/std::ctype::do_narrow
- xlocale/std::ctype::do_scan_is
- xlocale/std::ctype::do_scan_not
- xlocale/std::ctype::do_tolower
- xlocale/std::ctype::do_toupper
- xlocale/std::ctype::do_widen
- xlocale/std::ctype::is
- xlocale/std::ctype::narrow
- xlocale/std::ctype::scan_is
- xlocale/std::ctype::scan_not
- xlocale/std::ctype::tolower
- xlocale/std::ctype::toupper
- xlocale/std::ctype::widen
dev_langs:
- C++
helpviewer_keywords:
- std::ctype [C++]
- std::ctype [C++], char_type
- std::ctype [C++], do_is
- std::ctype [C++], do_narrow
- std::ctype [C++], do_scan_is
- std::ctype [C++], do_scan_not
- std::ctype [C++], do_tolower
- std::ctype [C++], do_toupper
- std::ctype [C++], do_widen
- std::ctype [C++], is
- std::ctype [C++], narrow
- std::ctype [C++], scan_is
- std::ctype [C++], scan_not
- std::ctype [C++], tolower
- std::ctype [C++], toupper
- std::ctype [C++], widen
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a65008b01262ad6252e9942444a4e80602d4292
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208641"
---
# <a name="ctype-class"></a>Класс ctype

Класс, предоставляющий аспект, используемый для классификации символов, преобразования из верхнего и нижнего регистра, а также преобразования между собственной кодировкой и кодировкой, используемой языковым стандартом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Параметры

*CharType* тип, используемый внутри программы для кодирования символов.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`. Критерии классификации получают вложенный тип битовой маски в базовом классе ctype_base.

Стандартная библиотека C++ определяет две явные специализации этого класса шаблона:

- [ctype](../standard-library/ctype-char-class.md)< `char`> — явная специализация, отличия которой описаны отдельно;

- **ctype**<`wchar_t`> — элементы обрабатываются как расширенные символы.

Другие специализации класса шаблона **ctype**\< **CharType**>:

- Преобразовать значение ***ch*** типа `CharType` значение типа **char** с выражением (`char`) **ch**.

- Преобразовать значение ***байтов*** типа **char** значение типа `CharType` с выражением **CharType** (**байтов**).

Все остальные операции выполняются на **char** значения таким же образом для явной специализации **ctype**<`char`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[ctype](#ctype)|Конструктор для объектов класса `ctype`, которые служат в качестве аспектов языкового стандарта для символов.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[char_type](#char_type)|Тип, который описывает символ, используемый языковым стандартом.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[do_is](#do_is)|Виртуальная функция, вызываемая для проверки того, есть ли у отдельного символа определенный атрибут, или для классификации атрибутов каждого символа в диапазоне и сохранения их в массиве.|
|[do_narrow](#do_narrow)|Виртуальная функция, вызываемая для преобразования символа типа `CharType` используемого языковым стандартом, в соответствующий символ типа **char** в собственной кодировке.|
|[do_scan_is](#do_scan_is)|Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.|
|[do_scan_not](#do_scan_not)|Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.|
|[do_tolower](#do_tolower)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.|
|[do_toupper](#do_toupper)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.|
|[do_widen](#do_widen)|Виртуальная функция, вызываемая для преобразует символ типа **char** в исходной кодировке в соответствующий символ типа `CharType` используемого языковым стандартом.|
|[is](#is)|Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.|
|[narrow](#narrow)|Преобразовывает символ типа `CharType`, используемый языковым стандартом, в соответствующий символ типа char в исходной кодировке.|
|[scan_is](#scan_is)|Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.|
|[scan_not](#scan_not)|Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.|
|[tolower](#tolower)|Преобразует символ или диапазон символов в нижний регистр.|
|[toupper](#toupper)|Преобразует символ или диапазон символов в верхний регистр.|
|[widen](#widen)|Преобразует символ типа **char** в исходной кодировке в соответствующий символ типа `CharType` используемого языковым стандартом.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="char_type"></a>  ctype::char_type

Тип, который описывает символ, используемый языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *CharType*.

### <a name="example"></a>Пример

Пример, в котором `char_type` используется в качестве возвращаемого значения, см. в описании функции-члена [widen](#widen).

## <a name="ctype"></a>  ctype::ctype

Конструктор для объектов класса ctype, которые служат в качестве аспектов языкового стандарта для символов.

```cpp
explicit ctype(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs* целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения *_Refs* параметра и их важность:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \> 1: эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект `locale::facet` с **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="do_is"></a>  ctype::do_is

Виртуальная функция, вызываемая для проверки того, есть ли у отдельного символа определенный атрибут, или для классификации атрибутов каждого символа в диапазоне и сохранения их в массиве.

```cpp
virtual bool do_is(
    mask maskVal,
    CharType ch) const;


virtual const CharType *do_is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски, для которого проверяемый символ.

*CH* символ, атрибуты которого должны тестироваться.

*Первый* указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*dest* указатель на начало массива, где будут храниться значения маски, характеризующие атрибуты каждого символа.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает логическое значение **true**, если протестированный символ имеет атрибут, описываемый значением маски, или значение **false**, если такой атрибут не удалось найти.

Вторая функция-член возвращает массив, содержащий значения маски, характеризующие атрибуты каждого символа в диапазоне.

### <a name="remarks"></a>Примечания

Значения маски, классифицирующие атрибуты символов, предоставляются классом [ctype_base](../standard-library/ctype-base-class.md), от которого производится класс ctype. Первая функция-член может принимать для своего первого параметра выражения, которые называются битовыми масками и формируются из сочетания значений маски логическими побитовыми операторами (&#124;, &, ^, ~).

### <a name="example"></a>Пример

См. пример для [is](#is), в котором вызывается `do_is`.

## <a name="do_narrow"></a>  ctype::do_narrow

Виртуальная функция, вызываемая для преобразования символа типа `CharType` используемого языковым стандартом, в соответствующий символ типа **char** в собственной кодировке.

```cpp
virtual char do_narrow(
    CharType ch,
    char default = '\0') const;


virtual const CharType* do_narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Параметры

*CH* символ типа `Chartype` используемой языковым стандартом для преобразования.

*по умолчанию* значение по умолчанию могут быть назначены функцией-членом символам типа `CharType` , не имеющих эквивалентных символов типа **char**.

*Первый* указатель на первый символ в диапазоне символов для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне символов для преобразования.

*dest* константный указатель на первый символ типа **char** в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция-член возвращает собственный символ типа char, соответствующий символу параметра типа `CharType` или *по умолчанию* Если эквивалент не задан.

Вторая защищенная функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Примечания

Вторая защищенная функция-член шаблона сохраняет в `dest`[ `I`] значение `do_narrow`( `first` [ `I`], `default`), для `I` в интервале [0, `last`  -  `first`).

### <a name="example"></a>Пример

См. пример для [narrow](#narrow), в котором вызывается `do_narrow`.

## <a name="do_scan_is"></a>  ctype::do_scan_is

Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски для сопоставления с символом.

*Первый* указатель на первый символ в просматриваемом диапазоне.

*последний* указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такое значение не существует, функция возвращает *последнего*.

### <a name="remarks"></a>Примечания

Защищенная функция-член возвращает наименьший указатель `ptr` в диапазоне [ `first`, `last`) для которой [do_is](#do_is)( `maskVal`, \* `ptr`) имеет значение true.

### <a name="example"></a>Пример

См. пример для [scan_is](#scan_is), в котором вызывается `do_scan_is`.

## <a name="do_scan_not"></a>  ctype::do_scan_not

Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски не для сопоставления с символом.

*Первый* указатель на первый символ в просматриваемом диапазоне.

*последний* указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такое значение не существует, функция возвращает *последнего*.

### <a name="remarks"></a>Примечания

Защищенная функция-член возвращает наименьший указатель `ptr` в диапазоне [ `first`, `last`) для которой [do_is](#do_is)( `maskVal`, \* `ptr`) имеет значение false.

### <a name="example"></a>Пример

См. пример для [scan_not](#scan_not), в котором вызывается `do_scan_not`.

## <a name="do_tolower"></a>  ctype::do_tolower

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.

```cpp
virtual CharType do_tolower(CharType ch) const;


virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*CH* символ для преобразования в нижний регистр.

*Первый* указатель на первый символ в диапазоне, регистр символов которого для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция-член возвращает строчной параметра *ch*. Если форма в нижнем регистре не существует, возвращается *ch*. Вторая защищенная функция-член возвращает *последнего*.

### <a name="remarks"></a>Примечания

Вторая функция защищенный член шаблона заменяет каждый элемент `first` [ `I`], для `I` в интервале [0, `last`  -  `first`), с помощью `do_tolower`( `first` [ `I`]).

### <a name="example"></a>Пример

См. пример для [tolower](#tolower), в котором вызывается `do_tolower`.

## <a name="do_toupper"></a>  ctype::do_toupper

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.

```cpp
virtual CharType do_toupper(CharType ch) const;


virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*CH* символ для преобразования в верхний регистр.

*Первый* указатель на первый символ в диапазоне, регистр символов которого для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция-член возвращает прописных букв параметра *ch*. Если форма в верхнем регистре не существует, возвращается *ch*. Вторая защищенная функция-член возвращает *последнего*.

### <a name="remarks"></a>Примечания

Вторая функция защищенный член шаблона заменяет каждый элемент `first` [ `I`], для `I` в интервале [0, `last`  -  `first`), с помощью `do_toupper`( `first` [ `I`]).

### <a name="example"></a>Пример

См. пример для [toupper](#toupper), в котором вызывается `do_toupper`.

## <a name="do_widen"></a>  ctype::do_widen

Виртуальная функция, вызываемая для преобразует символ типа **char** в исходной кодировке в соответствующий символ типа `CharType` используемого языковым стандартом.

```cpp
virtual CharType do_widen(char byte) const;


virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*байтов* символ типа **char** в исходной кодировке для преобразования.

*Первый* указатель на первый символ в диапазоне символов для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне символов для преобразования.

*dest* указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция-член возвращает символ типа `CharType` , соответствующий символу параметра исходного типа **char**.

Вторая защищенная функция-член возвращает указатель на целевой диапазон символов типа `CharType` используемого языковым стандартом, преобразованных из исходных символов типа **char**.

### <a name="remarks"></a>Примечания

Вторая защищенная функция-член шаблона сохраняет в `dest`[`I`] значение `do_widen`(`first`[`I`]) для `I` в диапазоне [0, `last` - `first`).

### <a name="example"></a>Пример

См. пример для [widen](#widen), в котором вызывается `do_widen`.

## <a name="is"></a>  ctype::is

Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.

```cpp
bool is(mask maskVal, CharType ch) const;


const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски, для которого проверяемый символ.

*CH* символ, атрибуты которого должны тестироваться.

*Первый* указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*dest* указатель на начало массива, где будут храниться значения маски, характеризующие атрибуты каждого символа.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает **true** Если протестированный символ имеет атрибут, описываемый значением маски, **false** Если не удалось найти атрибут.

Вторая функция-член возвращает указатель на последний символ в диапазоне, атрибуты которого должны классифицироваться.

### <a name="remarks"></a>Примечания

Значения маски, классифицирующие атрибуты символов, предоставляются классом [ctype_base](../standard-library/ctype-base-class.md), от которого производится класс ctype. Первая функция-член может принимать для своего первого параметра выражения, которые называются битовыми масками и формируются из сочетания значений маски логическими побитовыми операторами (&#124;, &, ^, ~).

### <a name="example"></a>Пример

```cpp
// ctype_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main() {
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );

   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;

   char *string = "Hello, my name is John!";
   ctype<char>::mask maskarray[30];
   use_facet<ctype<char> > ( loc2 ).is(
      string, string + strlen(string), maskarray );
   for (unsigned int i = 0; i < strlen(string); i++) {
      cout << string[i] << ": "
           << (maskarray[i] & ctype_base::alpha  "alpha"
                                                : "not alpha")
           << endl;;
   };
}
```

## <a name="narrow"></a>  ctype::narrow

Преобразовывает символы типа `CharType` используемого языковым стандартом, в соответствующие символы типа **char** в собственной кодировке.

```cpp
char narrow(CharType ch, char default = '\0') const;


const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Параметры

*CH* символ типа `Chartype` используемой языковым стандартом для преобразования.

*по умолчанию* значение по умолчанию могут быть назначены функцией-членом символам типа `CharType` , не имеющих эквивалентных символов типа **char**.

*Первый* указатель на первый символ в диапазоне символов для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне символов для преобразования.

*dest* константный указатель на первый символ типа **char** в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает собственный символ типа **char** , соответствующий символу параметра типа `CharType default` Если эквивалент не задан.

Вторая функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_narrow](#do_narrow)(`ch`, `default`). Вторая функция-член возвращает [do_narrow](#do_narrow) (`first`, `last`, `default`, `dest`). Только основные исходные символы всегда имеют уникальный прообраз `CharType` в `narrow`. Для этих базовых исходных символов хранится следующий инвариант: `narrow` ([widen](#widen) (**c**), 0) == **c**.

### <a name="example"></a>Пример

```cpp
// ctype_narrow.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "english" );
   wchar_t *str1 = L"\x0392fhello everyone";
   char str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996
   str2[wcslen(str1)] = '\0';
   wcout << str1 << endl;
   cout << &str2[0] << endl;
}
```

```Output
Xhello everyone
```

## <a name="scan_is"></a>  ctype::scan_is

Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски для сопоставления с символом.

*Первый* указатель на первый символ в просматриваемом диапазоне.

*последний* указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такое значение не существует, функция возвращает *последнего*.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_scan_is](#do_scan_is)(`maskVal`, `first`, `last`).

### <a name="example"></a>Пример

```cpp
// ctype_scan_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is
      ( ctype_base::punct, string, string + strlen(string) );
   cout << "The first punctuation is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
The first punctuation is "," at position: 5
```

## <a name="scan_not"></a>  ctype::scan_not

Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*maskVal* значение маски не для сопоставления с символом.

*Первый* указатель на первый символ в просматриваемом диапазоне.

*последний* указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такое значение не существует, функция возвращает *последнего*.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_scan_not](#do_scan_not)(`maskVal`, `first`, `last`).

### <a name="example"></a>Пример

```cpp
// ctype_scan_not.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not
      ( ctype_base::alpha, string, string + strlen(string) );
   cout << "First nonalpha character is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
First nonalpha character is "," at position: 5
```

## <a name="tolower"></a>  ctype::tolower

Преобразует символ или диапазон символов в нижний регистр.

```cpp
CharType tolower(CharType ch) const;


const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*CH* символ для преобразования в нижний регистр.

*Первый* указатель на первый символ в диапазоне, регистр символов которого для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает строчной параметра *ch*. Если форма в нижнем регистре не существует, возвращается *ch*.

Вторая функция-член возвращает *последнего*.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_tolower](#do_tolower)(`ch`). Вторая функция-член возвращает [do_tolower](#do_tolower)(`first`, `last`).

### <a name="example"></a>Пример

```cpp
// ctype_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "HELLO, MY NAME IS JOHN";

   use_facet<ctype<char> > ( loc1 ).tolower
      ( string, string + strlen(string) );
   cout << "The lowercase string is: " << string << endl;
}
```

```Output
The lowercase string is: hello, my name is john
```

## <a name="toupper"></a>  ctype::toupper

Преобразует символ или диапазон символов в верхний регистр.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*CH* символ для преобразования в верхний регистр.

*Первый* указатель на первый символ в диапазоне, регистр символов которого для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает прописных букв параметра *ch*. Если форма в верхнем регистре не существует, возвращается *ch*.

Вторая функция-член возвращает *последнего*.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_toupper](#do_toupper)(`ch`). Вторая функция-член возвращает [do_toupper](#do_toupper)(`first`, `last`).

### <a name="example"></a>Пример

```cpp
// ctype_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "Hello, my name is John";

   use_facet<ctype<char> > ( loc1 ).toupper
      ( string, string + strlen(string) );
   cout << "The uppercase string is: " << string << endl;
}
```

```Output
The uppercase string is: HELLO, MY NAME IS JOHN
```

## <a name="widen"></a>  ctype::widen

Преобразует символ типа **char** в исходной кодировке в соответствующий символ типа `CharType` используемого языковым стандартом.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*байтов* набора символов типа char в собственной кодировке для преобразования.

*Первый* указатель на первый символ в диапазоне символов для преобразования.

*последний* указатель на символ, следующий сразу за последним символом в диапазоне символов для преобразования.

*dest* указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает символ типа `CharType` , соответствующий символу параметра исходного типа **char**.

Вторая функция-член возвращает указатель на целевой диапазон символов типа `CharType` используемого языковым стандартом, преобразованных из исходных символов типа **char**.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_widen](#do_widen)(`byte`). Вторая функция-член возвращает [do_widen](#do_widen)(`first`, `last`, `dest`).

### <a name="example"></a>Пример

```cpp
// ctype_widen.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "English" );
   char *str1 = "Hello everyone!";
   wchar_t str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996
   str2[strlen(str1)] = '\0';
   cout << str1 << endl;
   wcout << &str2[0] << endl;

   ctype<wchar_t>::char_type charT;
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );
}
```

```Output
Hello everyone!
Hello everyone!
```

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

---
title: Класс ctype
ms.date: 11/04/2016
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
ms.openlocfilehash: dae6f62a0eda9263986a77b82754596d17be94e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373166"
---
# <a name="ctype-class"></a>Класс ctype

Класс, предоставляющий аспект, используемый для классификации символов, преобразования из верхнего и нижнего регистра, а также преобразования между собственной кодировкой и кодировкой, используемой языковым стандартом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов.

## <a name="remarks"></a>Remarks

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`. Критерии классификации получают вложенный тип битовой маски в базовом классе ctype_base.

Стандартная библиотека СЗ определяет две явные специализации этого шаблона класса:

- `ctype<char>`, явная специализация, различия которой описаны отдельно. Для получения дополнительной информации [см.&lt;&gt; ](../standard-library/ctype-char-class.md)

- `ctype<wchar_t>`, который рассматривает элементы как широкие символы.

Другие специализации `ctype<CharType>`шаблона класса:

- Преобразуйте значение *ch* типа *CharType* в значение `(char)ch` **символа** типа с выражением.

- Преобразуйте *значение байта* **символа** типа в значение `CharType(byte)`типа *CharType* с выражением.

Все остальные операции выполняются на значениях **char** так же, как и для явной специализации. `ctype<char>`

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[Ctype](#ctype)|Конструктор для объектов класса `ctype`, которые служат в качестве аспектов языкового стандарта для символов.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, который описывает символ, используемый языковым стандартом.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_is](#do_is)|Виртуальная функция, вызываемая для проверки того, есть ли у отдельного символа определенный атрибут, или для классификации атрибутов каждого символа в диапазоне и сохранения их в массиве.|
|[do_narrow](#do_narrow)|Виртуальная функция, призванная преобразовать символ типа, `CharType` используемого языком, в соответствующий символ **символа** типа в наборе символов.|
|[do_scan_is](#do_scan_is)|Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.|
|[do_scan_not](#do_scan_not)|Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.|
|[do_tolower](#do_tolower)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.|
|[do_toupper](#do_toupper)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.|
|[do_widen](#do_widen)|Виртуальная функция, называемая преобразованием символа **символа** типа в `CharType` родном символе, установленного в соответствующий символ типа, используемого языком.|
|[is](#is)|Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.|
|[narrow](#narrow)|Преобразовывает символ типа `CharType`, используемый языковым стандартом, в соответствующий символ типа char в исходной кодировке.|
|[scan_is](#scan_is)|Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.|
|[scan_not](#scan_not)|Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.|
|[токуэр](#tolower)|Преобразует символ или диапазон символов в нижний регистр.|
|[Toupper](#toupper)|Преобразует символ или диапазон символов в верхний регистр.|
|[widen](#widen)|Преобразует символ **символа** типа в родном символе, установленном в соответствующий символ типа, `CharType` используемого языком.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="ctypechar_type"></a><a name="char_type"></a>ctype::char_type

Тип, который описывает символ, используемый языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом для параметра-шаблона *Chartype*.

### <a name="example"></a>Пример

Пример, в котором `char_type` используется в качестве возвращаемого значения, см. в описании функции-члена [widen](#widen).

## <a name="ctypectype"></a><a name="ctype"></a>ctype::ctype

Конструктор для объектов класса ctype, которые служат в качестве аспектов языкового стандарта для символов.

```cpp
explicit ctype(size_t _Refs = 0);
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

Конструктор инициализирует свой базовый объект `locale::facet` с **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="ctypedo_is"></a><a name="do_is"></a>ctype::do

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

*маскаВал*\
Значение маски, для которого должен тестироваться символ.

*Ch*\
Символ, атрибуты которого должны тестироваться.

*Первый*\
Указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*Dest*\
Указатель на начало массива, где должны храниться значения маски, характеризующие атрибуты каждого из символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает логическое значение **true**, если протестированный символ имеет атрибут, описываемый значением маски, или значение **false**, если такой атрибут не удалось найти.

Вторая функция-член возвращает массив, содержащий значения маски, характеризующие атрибуты каждого символа в диапазоне.

### <a name="remarks"></a>Remarks

Значения маски, классифицирующие атрибуты символов, предоставляются классом [ctype_base](../standard-library/ctype-base-class.md), от которого производится класс ctype. Первая функция-член может принимать для своего первого параметра выражения, которые называются битовыми масками и формируются из сочетания значений маски логическими побитовыми операторами (&#124;, &, ^, ~).

### <a name="example"></a>Пример

См. пример для [is](#is), в котором вызывается `do_is`.

## <a name="ctypedo_narrow"></a><a name="do_narrow"></a>ctype::do-narrow

Виртуальная функция, призванная преобразовать символ типа, `CharType` используемого языком, в соответствующий символ **символа** типа в наборе символов.

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

*Ch*\
Символ типа `Chartype`, используемого языковым стандартом, который требуется преобразовать.

*По умолчанию*\
Значение по умолчанию, которое должно быть присвоено функцией участника символам типа, `CharType` не имеющие символы аналогов **символа символа**типа ..

*Первый*\
Указатель на первый символ в диапазоне символов для преобразования.

*Последний*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*Dest*\
Конст указатель на первый символ типа **символ** в диапазоне назначения, который хранит преобразованный диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция члена возвращает родной символ символа типа, который соответствует параметру типа `CharType` или по *умолчанию,* если не определен аналог.

Вторая защищенная функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Remarks

Второй защищенный шаблон члена `dest` `I`функции `do_narrow`магазинов в й значение `first` ( , `last`  -  `first` `I` `default`, для `I` в интервале 0, ).

### <a name="example"></a>Пример

См. пример для [narrow](#narrow), в котором вызывается `do_narrow`.

## <a name="ctypedo_scan_is"></a><a name="do_scan_is"></a>ctype::do'scan

Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*маскаВал*\
Значение маски для сопоставления с символом.

*Первый*\
Указатель на первый символ в просматриваемом диапазоне символов.

*Последний*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такого значения не существует, функция возвращается *в последнюю величину.*

### <a name="remarks"></a>Remarks

Защищенная `ptr` функция члена возвращает наименьший `first`указатель в диапазоне \* `ptr`, `last`для которого [do_is](#do_is)(, `maskVal`) верно.

### <a name="example"></a>Пример

См. пример для [scan_is](#scan_is), в котором вызывается `do_scan_is`.

## <a name="ctypedo_scan_not"></a><a name="do_scan_not"></a>ctype::do'scan

Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*маскаВал*\
Значение маски, которому не должен соответствовать символ.

*Первый*\
Указатель на первый символ в просматриваемом диапазоне символов.

*Последний*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такого значения не существует, функция возвращается *в последнюю величину.*

### <a name="remarks"></a>Remarks

Защищенная `ptr` функция члена возвращает наименьший `first`указатель в диапазоне \* `ptr`, `last`для которого [do_is](#do_is)(, `maskVal`) является ложным.

### <a name="example"></a>Пример

См. пример для [scan_not](#scan_not), в котором вызывается `do_scan_not`.

## <a name="ctypedo_tolower"></a><a name="do_tolower"></a>ctype::do'tolower

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ для преобразования в нижний регистр.

*Первый*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция члена возвращает форму нижнего регистра параметра *ch.* Если не существует нижнего регистра, он возвращает *ch*. Вторая защищенная функция члена *возвращается в последний раз.*

### <a name="remarks"></a>Remarks

Вторая защищенная функция шаблона `first` `I`члена заменяет каждый элемент, для `I` в интервале 0, `last`  -  `first`с `do_tolower`(no). `first` `I`

### <a name="example"></a>Пример

См. пример для [tolower](#tolower), в котором вызывается `do_tolower`.

## <a name="ctypedo_toupper"></a><a name="do_toupper"></a>ctype::do'toupper

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ для преобразования в верхний регистр.

*Первый*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция члена возвращает форму верхнего регистра параметра *ch.* Если нет верхней формы существует, он возвращает *ч*. Вторая защищенная функция члена *возвращается в последний раз.*

### <a name="remarks"></a>Remarks

Вторая защищенная функция шаблона `first` `I`члена заменяет каждый элемент, для `I` в интервале 0, `last`  -  `first`с `do_toupper`(no). `first` `I`

### <a name="example"></a>Пример

См. пример для [toupper](#toupper), в котором вызывается `do_toupper`.

## <a name="ctypedo_widen"></a><a name="do_widen"></a>ctype::do-widen

Виртуальная функция, называемая преобразованием символа **символа** типа в `CharType` родном символе, установленного в соответствующий символ типа, используемого языком.

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*Байт*\
Характер **символа** типа в родном символе, который должен быть преобразован.

*Первый*\
Указатель на первый символ в диапазоне символов для преобразования.

*Последний*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*Dest*\
Указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая защищенная функция члена `CharType` возвращает символ типа, который соответствует параметру символа родного **типа char.**

Вторая защищенная функция члена возвращает указатель в диапазон `CharType` назначения символов типа, используемого языком, преобразованным из местных символов символа **типа.**

### <a name="remarks"></a>Remarks

Вторая защищенная функция-член шаблона сохраняет в `dest`[`I`] значение `do_widen`(`first`[`I`]) для `I` в диапазоне [0, `last` - `first`).

### <a name="example"></a>Пример

См. пример для [widen](#widen), в котором вызывается `do_widen`.

## <a name="ctypeis"></a><a name="is"></a>ctype::is

Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Параметры

*маскаВал*\
Значение маски, для которого должен тестироваться символ.

*Ch*\
Символ, атрибуты которого должны тестироваться.

*Первый*\
Указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*Dest*\
Указатель на начало массива, где должны храниться значения маски, характеризующие атрибуты каждого из символов.

### <a name="return-value"></a>Возвращаемое значение

Функция первого члена **возвращается,** если тестируемый символ имеет атрибут, описанный значением маски; **ложно,** если у него не может быть атрибута.

Вторая функция-член возвращает указатель на последний символ в диапазоне, атрибуты которого должны классифицироваться.

### <a name="remarks"></a>Remarks

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

## <a name="ctypenarrow"></a><a name="narrow"></a>ctype::узкий

Преобразует символы типа, `CharType` используемого языком, в соответствующие символы **символа** символа в наборе символов.

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ типа `Chartype`, используемого языковым стандартом, который требуется преобразовать.

*По умолчанию*\
Значение по умолчанию, которое должно быть присвоено функцией участника символам типа, `CharType` не имеющие символы аналогов **символа символа**типа ..

*Первый*\
Указатель на первый символ в диапазоне символов для преобразования.

*Последний*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*Dest*\
Конст указатель на первый символ типа **символ** в диапазоне назначения, который хранит преобразованный диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Функция первого члена возвращает родной символ **символа** типа, `CharType default` который соответствует параметру типа типа, если не аналог определен.

Вторая функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Remarks

Функция первого члена`ch` [возвращается do_narrow](#do_narrow)(, ). `default` Функция второго члена`first`возвращает `last` `default`do_narrow `dest`(, , . . [do_narrow](#do_narrow) Только основные исходные символы всегда имеют уникальный прообраз `CharType` в `narrow`. Для этих базовых исходных символов хранится следующий инвариант: `narrow` ([widen](#widen) (**c**), 0) == **c**.

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

## <a name="ctypescan_is"></a><a name="scan_is"></a>ctype::scan_is

Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*маскаВал*\
Значение маски для сопоставления с символом.

*Первый*\
Указатель на первый символ в просматриваемом диапазоне символов.

*Последний*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такого значения не существует, функция возвращается *в последнюю величину.*

### <a name="remarks"></a>Remarks

Функция участника [do_scan_is](#do_scan_is)возвращает`maskVal`do_scan_is `first` `last`(, , ).

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

## <a name="ctypescan_not"></a><a name="scan_not"></a>ctype::scan_not

Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*маскаВал*\
Значение маски, которому не должен соответствовать символ.

*Первый*\
Указатель на первый символ в просматриваемом диапазоне символов.

*Последний*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такого значения не существует, функция возвращается *в последнюю величину.*

### <a name="remarks"></a>Remarks

Функция участника [do_scan_not](#do_scan_not)возвращает`maskVal`do_scan_not `first` `last`(, , ).

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

## <a name="ctypetolower"></a><a name="tolower"></a>ctype::tolower

Преобразует символ или диапазон символов в нижний регистр.

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ для преобразования в нижний регистр.

*Первый*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Функция первого члена возвращает форму нижнего регистра параметра *ch.* Если не существует нижнего регистра, он возвращает *ch*.

Функция второго члена возвращается *в последний раз.*

### <a name="remarks"></a>Remarks

Функция первого [do_tolower](#do_tolower)члена`ch`возвращает do_tolower (). Функция второго члена`first` [возвращается do_tolower](#do_tolower)(, ). `last`

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

## <a name="ctypetoupper"></a><a name="toupper"></a>ctype::toupper

Преобразует символ или диапазон символов в верхний регистр.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ для преобразования в верхний регистр.

*Первый*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*Последний*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Функция первого члена возвращает форму верхнего регистра параметра *ch.* Если нет верхней формы существует, он возвращает *ч*.

Функция второго члена возвращается *в последний раз.*

### <a name="remarks"></a>Remarks

Функция первого члена`ch` [возвращается do_toupper](#do_toupper)(). Функция второго члена `first` [возвращается do_toupper](#do_toupper)(, ). `last`

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

## <a name="ctypewiden"></a><a name="widen"></a>ctype:widen

Преобразует символ **символа** типа в родном символе, установленном в соответствующий символ типа, `CharType` используемого языком.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*Байт*\
Символ типа char в исходной кодировке для преобразования.

*Первый*\
Указатель на первый символ в диапазоне символов для преобразования.

*Последний*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*Dest*\
Указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Функция первого члена возвращает `CharType` символ типа, который соответствует параметру символа родного **символа**типа.

Функция второго члена возвращает указатель в диапазон назначения `CharType` символов типа, используемого языком, преобразованным из местных символов символа типа **char.**

### <a name="remarks"></a>Remarks

Функция первого члена`byte` [возвращается do_widen](#do_widen)(). Функция второго члена`first` [возвращается do_widen](#do_widen)(, `last`, ). `dest`

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

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

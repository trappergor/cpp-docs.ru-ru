---
title: Класс collate
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate
- locale/std::collate::char_type
- locale/std::collate::string_type
- locale/std::collate::compare
- locale/std::collate::do_compare
- locale/std::collate::do_hash
- locale/std::collate::do_transform
- locale/std::collate::hash
- locale/std::collate::transform
helpviewer_keywords:
- std::collate [C++]
- std::collate [C++], char_type
- std::collate [C++], string_type
- std::collate [C++], compare
- std::collate [C++], do_compare
- std::collate [C++], do_hash
- std::collate [C++], do_transform
- std::collate [C++], hash
- std::collate [C++], transform
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
ms.openlocfilehash: c506a6a2e1e2c0610f8a6129d2bfb42f762e998a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458607"
---
# <a name="collate-class"></a>Класс collate

Класс шаблона, описывающий объект, который может использоваться как аспект языкового стандарта для управления порядком и группированием символов в строке, их сравнением и хэшированием строк.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`. В одних языка символы группируются и обрабатываются как один символ, в других отдельные символы обрабатываются так, как если бы каждый из них представлял собой два символа. Службы упорядочивания, предоставленные классом collate, обеспечивают способ сортировки в таких случаях.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[collate](#collate)|Конструктор для объектов класса `collate`, который служит в качестве аспекта языкового стандарта для обработки преобразований сортировки строк.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, описывающий символ типа `CharType`.|
|[string_type](#string_type)|Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[compare](#compare)|Проверяет две последовательности символов на равенство или неравенство в соответствии с правилами для конкретных аспектов.|
|[do_compare](#do_compare)|Виртуальная функция, вызываемая для проверки двух последовательностей символов на равенство или неравенство в соответствии с правилами для конкретных аспектов.|
|[do_hash](#do_hash)|Виртуальная функция, вызываемая для определения хэш-значения последовательностей в соответствии с правилами для конкретных аспектов.|
|[do_transform](#do_transform)|Виртуальная функция, вызываемая для преобразования последовательности символов из языкового стандарта в строку, которая может быть использована для лексикографического сравнения с другими последовательностями символов, аналогичным образом преобразованными из того же языкового стандарта.|
|[hash](#hash)|Определяет хэш-значение последовательности в соответствии с правилами для конкретных аспектов.|
|[transform](#transform)|Преобразует последовательность символов из языкового стандарта в строку, которая может быть использована для лексикографического сравнения с другими последовательностями символов, аналогичным образом преобразованными из того же языкового стандарта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="char_type"></a>  collate::char_type

Тип, описывающий символ типа `CharType`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="collate"></a>  collate::collate

Конструктор для объектов класса collate, который служит в качестве аспекта языкового стандарта для обработки преобразований сортировки строк.

```cpp
public:
    explicit collate(
    size_t _Refs = 0);

protected:
    collate(
const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

*_Locname*\
Имя языкового стандарта.

### <a name="remarks"></a>Примечания

Возможные значения для параметра *_Refs* и их значимость:

- 0,0 Время существования объекта управляется языками, содержащими его.

- 1: Время существования объекта должно быть управляемым вручную.

- \>1: Эти значения не определены.

Конструктор инициализирует свой базовый объект с **локальным::** [Facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="compare"></a>  collate::compare

Проверяет две последовательности символов на равенство или неравенство в соответствии с правилами для конкретных аспектов.

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Параметры

*first1*\
Указатель на первый элемент в первой последовательности для сравнения.

*last1*\
Указатель на последний элемент в первой последовательности для сравнения.

*first2*\
Указатель на первый элемент во второй последовательности для сравнения.

*last2*\
Указатель на последний элемент во второй последовательности для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает:

- –1, если первая последовательность оказывается меньше, чем вторая;

- +1, если вторая последовательность оказывается меньше, чем первая;

- 0, если последовательности являются эквивалентными.

### <a name="remarks"></a>Примечания

Первая последовательность оценивается как меньшая, если в ней находится меньший элемент в первой неравной паре значений последовательностей или если неравные пары отсутствуют, но первая последовательность короче.

Функция-член возвращает [do_compare](#do_compare)(`first1`, `last1`, `first2`, `last2`).

### <a name="example"></a>Пример

```cpp
// collate_compare.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare ( s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result2 << endl;
}
```

## <a name="do_compare"></a>  collate::do_compare

Виртуальная функция, вызываемая для проверки двух последовательностей символов на равенство или неравенство в соответствии с правилами для конкретных аспектов.

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>Параметры

*first1*\
Указатель на первый элемент в первой последовательности для сравнения.

*last1*\
Указатель на последний элемент в первой последовательности для сравнения.

*first2*\
Указатель на первый элемент во второй последовательности для сравнения.

*last2*\
Указатель на последний элемент во второй последовательности для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает:

- –1, если первая последовательность оказывается меньше, чем вторая;

- +1, если вторая последовательность оказывается меньше, чем первая;

- 0, если последовательности являются эквивалентными.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член сравнивает последовательность в [* first1, last1) * с последовательностью в *[first2, last2*). Он сравнивает значения, применяя `operator<` между парами соответствующих элементов типа. `CharType` Первая последовательность оценивается как меньшая, если в ней находится меньший элемент в первой неравной паре значений последовательностей или если неравные пары отсутствуют, но первая последовательность короче.

### <a name="example"></a>Пример

См. пример для [collate::compare](#compare), в котором вызывается метод `do_compare`.

## <a name="do_hash"></a>  collate::do_hash

Виртуальная функция, вызываемая для определения хэш-значения последовательностей в соответствии с правилами для конкретных аспектов.

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*началь*\
Указатель на первый символ в последовательности, чье хэш-значение требуется определить.

*Последняя*\
Указатель на последний символ в последовательности, чье хэш-значение требуется определить.

### <a name="return-value"></a>Возвращаемое значение

Хэш-значение типа **long** для последовательности.

### <a name="remarks"></a>Примечания

Хэш-значение может быть полезно, например при псевдослучайном распределении последовательностей по массиву списков.

### <a name="example"></a>Пример

См. пример для [hash](#hash), в котором вызывается `do_hash`.

## <a name="do_transform"></a>  collate::do_transform

Виртуальная функция, вызываемая для преобразования последовательности символов из языкового стандарта в строку, которая может быть использована для лексикографического сравнения с другими последовательностями символов, аналогичным образом преобразованными из того же языкового стандарта.

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*началь*\
Указатель на первый символ в преобразуемой последовательности.

*Последняя*\
Указатель на последний символ в преобразуемой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Строка, представляющая преобразованную последовательность символов.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член возвращает объект класса [string_type](#string_type), управляемая последовательность которого является копией последовательности [`first`, `last`). Если класс, производный от collate\< **CharType**>, переопределяет [do_compare](#do_compare), следует также переопределить `do_transform` для соответствия. При передаче в `collate::compare` две преобразованные строки должны дать тот же результат, который был бы получен при передаче непреобразованных строк для сравнения в производном классе.

### <a name="example"></a>Пример

См. пример для [transform](#transform), в котором вызывается `do_transform`.

## <a name="hash"></a>  collate::hash

Определяет хэш-значение последовательности в соответствии с правилами для конкретных аспектов.

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*началь*\
Указатель на первый символ в последовательности, чье хэш-значение требуется определить.

*Последняя*\
Указатель на последний символ в последовательности, чье хэш-значение требуется определить.

### <a name="return-value"></a>Возвращаемое значение

Хэш-значение типа **long** для последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_hash](#do_hash)(`first`, `last`).

Хэш-значение может быть полезно, например при псевдослучайном распределении последовательностей по массиву списков.

### <a name="example"></a>Пример

```cpp
// collate_hash.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("\x00dfzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet
   _TCHAR * s2 = _T("zzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet

   long r1 = use_facet< collate<_TCHAR> > ( loc ).
      hash (s1, &s1[_tcslen( s1 )-1 ]);
   long r2 =  use_facet< collate<_TCHAR> > ( loc ).
      hash (s2, &s2[_tcslen( s2 )-1 ] );
   cout << r1 << " " << r2 << endl;
}
```

```Output
541187293 551279837
```

## <a name="string_type"></a>  collate::string_type

Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию класса-шаблона [basic_string](../standard-library/basic-string-class.md), объекты которого могут хранить копии исходной последовательности.

### <a name="example"></a>Пример

См. пример объявления и использования `string_type` в разделе [transform](#transform).

## <a name="transform"></a>  collate::transform

Преобразует последовательность символов из языкового стандарта в строку, которая может быть использована для лексикографического сравнения с другими последовательностями символов, аналогичным образом преобразованными из того же языкового стандарта.

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*началь*\
Указатель на первый символ в преобразуемой последовательности.

*Последняя*\
Указатель на последний символ в преобразуемой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая преобразованную последовательность символов.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_transform](#do_transform)(`first`, `last`).

### <a name="example"></a>Пример

```cpp
// collate_transform.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   _TCHAR* s1 = _T("\x00dfzz abc.");
   // \x00df is the German sharp-s (looks like beta),
   // it comes before z in the alphabet
   _TCHAR* s2 = _T("zzz abc.");

   collate<_TCHAR>::string_type r1;   // OK for typedef
   r1 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s1, &s1[_tcslen( s1 )-1 ]);

   cout << r1 << endl;

   basic_string<_TCHAR> r2 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s2, &s2[_tcslen( s2 )-1 ]);

   cout << r2 << endl;

   int result1 = use_facet<collate<_TCHAR> > ( loc ).compare
      (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );

   cout << _tcscmp(r1.c_str( ),r2.c_str( )) << result1
      << _tcscmp(s1,s2) <<endl;
}
```

```Output

-1-11
```

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

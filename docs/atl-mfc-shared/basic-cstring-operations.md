---
title: Базовые операции CString
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: 68947dc37e5398ac7caa4754e9af40223cec7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317961"
---
# <a name="basic-cstring-operations"></a>Базовые операции CString

Эта тема объясняет следующие основные операции [CString:](../atl-mfc-shared/reference/cstringt-class.md)

- [Создание объектов CString из стандартных буквальных строк C](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Доступ к отдельным символам в CString](#_core_accessing_individual_characters_in_a_cstring)

- [Совмещение двух объектов CString](#_core_concatenating_two_cstring_objects)

- [Сравнение объектов CString](#_core_comparing_cstring_objects)

- [Преобразование объектов CString](#_core_converting_cstring_objects)

`Class CString`основан на шаблоне класса [CStringT Class.](../atl-mfc-shared/reference/cstringt-class.md) `CString`является **typedef** `CStringT`. Точнее, `CString` это **typedef** *явной специализации* `CStringT`, которая является распространенным способом использования шаблона класса для определения класса. Аналогичным образом `CStringA` определенные классы и `CStringW`.

`CString`, `CStringA`, `CStringW` и определяются в atlstr.h. `CStringT`определяется в cstringt.h.

`CString`, `CStringA`, `CStringW` и каждый получить набор методов `CStringT` и операторов, определенных для использования со строкой данных, которые они поддерживают. Некоторые методы дублируют и в некоторых случаях превосходят строковые службы библиотек c., проводимых в течение выполнения.

Примечание: `CString` является родным классом. Для класса строк, предназначенного для использования в управляемом проекте с c-/CLI, используйте `System.String`.

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>Создание cString объектов из стандартных C литературных струн

Вы можете назначить буквальные строки `CString` в стиле C так `CString` же, как вы можете назначить один объект другому.

- Присвоить объекту значение буквальной `CString` строки C.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Присвоите значение `CString` одного `CString` другому объекту.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Содержимое `CString` объекта копируется при `CString` присвоении одному объекту другого объекта. Таким образом, две строки не имеют общего ссылки на фактические символы, которые составляют строку. Для получения дополнительной информации о том, как использовать `CString` объекты в качестве значений, см. [CString Semantics](../atl-mfc-shared/cstring-semantics.md)

   > [!NOTE]
   > Чтобы написать приложение так, чтобы оно можно было компилировать для Unicode или для ANSI, закодируйте буквальные строки с помощью _T макроса. Для получения дополнительной информации [см.](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>Доступ к отдельным персонажам в CString

Вы можете получить доступ `CString` к отдельным `GetAt` символам в объекте с помощью `SetAt` и методов. Вы также можете использовать элемент массива, или subscript, `GetAt` оператор (я) вместо того, чтобы получить отдельные символы. (Это напоминает доступ к элементам массива по индексу, как в стандартных строках C-стиля.) Значения индекса `CString` для символов на уровне нуля.

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>Совмещение двух объектов CString

Для конкатации двух `CString` объектов используйте операторы конкатации (яп. ) используйте следующие.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

По крайней мере один аргумент для операторов конкатации (я) должен быть объектом, `CString` `"big"`но вы можете использовать постоянную строку символов (например, ) или **символ** (например, 'x') для другого аргумента.

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>Сравнение объектов CString

Метод `Compare` и оператор q» `CString` для эквивалентны. `Compare`, **оператор ,** `CompareNoCase` и являются MBCS и Unicode известно; `CompareNoCase` также нечувствительны мейксонал. Метод `Collate` `CString` является локально чувствительным и часто `Compare`медленнее, чем . Используйте `Collate` только там, где вы должны соблюдать правила сортировки, указанные в текущем локалье.

В следующей таблице показаны доступные функции сравнения [CString](../atl-mfc-shared/reference/cstringt-class.md) и их эквивалентные функции Unicode/MBCS-портативных в библиотеке C run-time.

|Функция CString|Функция MBCS|Функция Unicode|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

Шаблон `CStringT` класса определяет реляционные операторы (<, \<>, >, и !), которые доступны `CString`для использования . Вы можете `CStrings` сравнить два с помощью этих операторов, как показано в следующем примере.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>Преобразование объектов CString

Для получения информации о преобразовании объектов CString в другие типы строк [см.](../text/how-to-convert-between-various-string-types.md)

## <a name="using-cstring-with-wcout"></a>Использование CString с wcout

Чтобы использовать CString `wcout` с помощью вас необходимо `const wchar_t*` явно бросить объект на показано в следующем примере:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

Без литых, `cs` рассматривается как `void*` и `wcout` печатает адрес объекта. Такое поведение вызвано тонкими взаимодействиями между вычетом аргументов шаблона и разрешением перегрузок, которые сами по себе являются правильными и совместимыми со стандартом C.

## <a name="see-also"></a>См. также раздел

[Струны (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Специализация шаблонов](../cpp/template-specialization-cpp.md)<br/>
[Практическое руководство. Преобразование различных типов строк](../text/how-to-convert-between-various-string-types.md)

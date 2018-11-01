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
ms.openlocfilehash: d1f16e470123bd52cb2656541aafaabdfc16af8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434079"
---
# <a name="basic-cstring-operations"></a>Базовые операции CString

В этом разделе объясняется следующим базовым [CString](../atl-mfc-shared/reference/cstringt-class.md) операций:

- [Создание объектов CString из стандартных строковых литералов C](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Доступ к отдельным символам в CString](#_core_accessing_individual_characters_in_a_cstring)

- [Объединение двух объектов CString](#_core_concatenating_two_cstring_objects)

- [Сравнение объектов CString](#_core_comparing_cstring_objects)

- [Преобразование объектов CString](#_core_converting_cstring_objects)

`Class CString` на основе шаблона класса [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md). `CString` — **typedef** из `CStringT`. Более точно `CString` — **typedef** из *явная специализация* из `CStringT`, который является стандартным способом использования шаблона класса для определения класса. Аналогичным образом определенных классов являются `CStringA` и `CStringW`.

`CString`, `CStringA`, и `CStringW` определяются в atlstr.h. `CStringT` определяется в cstringt.h.

`CString`, `CStringA`, и `CStringW` каждого получить набор методов и операторы, определенные `CStringT` для использования со строковыми данными, они поддерживают. Некоторые методы повторяющиеся и, в некоторых случаях преодолеть служб строку из библиотеки времени выполнения C.

Примечание: `CString` — это собственный класс. Для класса строки, который предназначен для использования в C + +/ CLI управляемый проект, используйте `System.String`.

##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Создание объектов CString из строковых литералов в стандартном языке C

Вы можете назначить строковыми литералами C-стиля для `CString` так же, как можно назначить одно `CString` объект с другим объектом.

- Назначьте C текстовую строку, `CString` объекта.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Назначьте один `CString` в другой `CString` объекта.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Содержание `CString` объект копируются в том случае, если в одном `CString` присваивается объект в другой. Таким образом две строки, не используйте ссылку на фактическое символы, составляющие строку. Дополнительные сведения об использовании `CString` объектов в качестве значения, см. в разделе [семантика CString](../atl-mfc-shared/cstring-semantics.md).

   > [!NOTE]
   > Чтобы писать приложения таким образом, чтобы его можно скомпилировать для Юникода или ANSI, строковые литералы кода с помощью макрос _T. Дополнительные сведения см. в разделе [многобайтовых кодировку (MBCS) поддержка Юникода и](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Доступ к отдельным символам в CString

Можно получить доступ к отдельным символам в `CString` объекта с помощью `GetAt` и `SetAt` методы. Можно также использовать массив элемент, индекс, оператор или ([]) вместо `GetAt` для получения отдельных символов. (Доступ к элементам массива напоминает Index, как в стандартной строки в стиле C). Индексировать значения для `CString` символов отсчитываются от нуля.

##  <a name="_core_concatenating_two_cstring_objects"></a> Объединение двух объектов CString

Для сцепления двух `CString` объекты, используют операторы объединения (+ или +=), как показано ниже.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

Хотя бы один аргумент для оператора объединения (+ или +=) должен быть `CString` объекта, но можно использовать на постоянную строку символов (например, `"big"`) или **char** (например, «x») для второго аргумента.

##  <a name="_core_comparing_cstring_objects"></a> Сравнение объектов CString

`Compare` Метод и ==-оператор для `CString` эквивалентны. `Compare`, **оператор ==**, и `CompareNoCase` известно многобайтовой Кодировки и Юникода; `CompareNoCase` также не учитывается регистр. `Collate` Метод `CString` зависящие от языкового стандарта и часто выполняется медленнее, чем `Compare`. Используйте `Collate` только когда вы должны соблюдать порядок сортировки правила согласно текущим языковым стандартом.

В следующей таблице показаны доступные [CString](../atl-mfc-shared/reference/cstringt-class.md) сравнение функций и их эквивалентные функции переносимой Юникода и Многобайтовой кодировкой в библиотеке времени выполнения C.

|CString-функция|MBCS-функция|Функции Юникода|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT` Класс шаблона определяет реляционные операторы (<, \<=, > =, >, ==, и! =), которые доступны для использования `CString`. Вы можете сравнить два `CStrings` с помощью этих операторов, как показано в следующем примере.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

##  <a name="_core_converting_cstring_objects"></a> Преобразование объектов CString

Сведения о преобразовании объекты CString в строки других типов, см. в разделе [как: преобразование между различных типов строк](../text/how-to-convert-between-various-string-types.md).

## <a name="using-cstring-with-wcout"></a>Использование CString с wcout

Использование CString с `wcout` необходимо явно привести объект к `const wchar_t*` как показано в следующем примере:

```
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;

```

Без приведения `cs` рассматривается как `void*` и `wcout` выводит адрес объекта. Такое поведение связано с тонкие взаимодействия между шаблона удержания и перегрузки разрешение аргументов в самих правильный и соответствовали стандарту C++.

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Специализация шаблонов](../cpp/template-specialization-cpp.md)<br/>
[Практическое руководство. Преобразование различных типов строк](../text/how-to-convert-between-various-string-types.md)


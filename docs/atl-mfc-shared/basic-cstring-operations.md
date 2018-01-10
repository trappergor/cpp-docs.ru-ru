---
title: "Базовые операции CString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42353a9c59bead96da8eb3b114c8acb2361b53d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="basic-cstring-operations"></a>Базовые операции CString
В этом разделе объясняется следующим базовым [CString](../atl-mfc-shared/reference/cstringt-class.md) операций:  
  
- [Создание объектов CString из стандартных строковых литералов C](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
- [Доступ к отдельным символам в CString](#_core_accessing_individual_characters_in_a_cstring)  
  
- [Объединение двух объектов CString](#_core_concatenating_two_cstring_objects)  
  
- [Сравнение объектов CString](#_core_comparing_cstring_objects)  
  
- [Преобразование объектов CString](#_core_converting_cstring_objects)  
  
 `Class CString`на основе шаблона класса [класс CStringT](../atl-mfc-shared/reference/cstringt-class.md). `CString`— `typedef` из `CStringT`. Более точно `CString` — `typedef` из *явная специализация* из `CStringT`, который является простой способ использования шаблона класса для определения класса. Аналогичным образом определенных классов являются `CStringA` и `CStringW`.  
  
 `CString`, `CStringA`, и `CStringW` определены в atlstr.h. `CStringT`определено в cstringt.h.  
  
 `CString`, `CStringA`, и `CStringW` каждого получить набор методов и операторы, определяемые `CStringT` для использования с строковые данные, которые они поддерживают. Некоторые методы повторяющиеся и, в некоторых случаях превосходит служб строку из библиотеки времени выполнения C.  
  
 Примечание: `CString` — это собственный класс. Для класса строки, который предназначен для использования в C + +/ CLI управляемый проект, используйте `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>Создание объектов CString из строковых литералов в стандартном языке C  
 Можно назначить строковыми литералами C-стиле для `CString` так же, как вы назначаете `CString` объекта в другой.  
  
-   Присвойте значение C строковый литерал `CString` объекта.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]  
  
-   Присвойте значение одного `CString` в другой `CString` объекта.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]  
  
     Содержимое `CString` объекта копируются в том случае, когда один `CString` назначить объект в другой. Таким образом две строки не будут использовать ссылку на фактические символы, которые составляют строку. Дополнительные сведения об использовании `CString` объекты как значения, см. [семантика CString](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  Чтобы писать приложения таким образом, чтобы он может компилироваться для Юникода или ANSI, строки литералов кода с помощью макрос _T. Дополнительные сведения см. в разделе [задать многобайтовых символов (MBCS) поддержка Юникода и](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a>Доступ к отдельным символам в CString  
 Можно получить доступ к отдельным символам в `CString` объектов с помощью `GetAt` и `SetAt` методы. Можно также использовать массив элемент, индекс, оператор или ([]) вместо `GetAt` для получения отдельных символов. (Доступ к элементам массива напоминает Index, как и стандартные строки в стиле C). Индекс значения для `CString` символов отсчитываются от нуля.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a>Объединение двух объектов CString  
 Для сцепления двух `CString` объектов, используйте операторы объединения (+ или +=), как показано ниже.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]  
  
 Хотя бы один аргумент для оператора объединения (+ или +=) должен быть `CString` объекта, но можно использовать на постоянную строку символов (например, `"big"`) или `char` (например, «x») для второго аргумента.  
  
##  <a name="_core_comparing_cstring_objects"></a>Сравнение объектов CString  
 `Compare` Метода и оператор == `CString` эквивалентны. `Compare`, `operator==`, и `CompareNoCase` учитывают многобайтовой Кодировки и Юникода; `CompareNoCase` также не учитывается. `Collate` Метод `CString` зависящие от языкового стандарта и часто выполняется медленнее, чем `Compare`. Используйте `Collate` только которых необходимо придерживаться сортировки правил в соответствии с текущего языкового стандарта.  
  
 В следующей таблице показаны доступные [CString](../atl-mfc-shared/reference/cstringt-class.md) сравнение функций и их эквивалентные функции библиотеки времени выполнения C переносимой Юникода и Многобайтовой кодировкой.  
  
|CString-функция|MBCS-функция|Функция Юникода|  
|----------------------|-------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT` Шаблона класса определяет реляционные операторы (<, \<=, > =, >, ==, и! =), они доступны для использования `CString`. Можно сравнить два `CStrings` с помощью этих операторов, как показано в следующем примере.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a>Преобразование объектов CString  
 Сведения о преобразовании CString-объекты для строк остальных типов см. в разделе [как: преобразование между различных типов строк](../text/how-to-convert-between-various-string-types.md).  
  
## <a name="using-cstring-with-wcout"></a>Использование CString с wcout  
 Использование CString с `wcout` необходимо явно привести объект к `const wchar_t*` как показано в следующем примере:  
  
```  
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
 
```  
  
 Без приведения `cs` рассматривается как `void*` и `wcout` выводит адреса объекта. Это поведение связано с слабая взаимодействий между шаблона удержания и перегрузка разрешение аргументов в самих правильный и соответствовали стандарту C++.  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)   
 [Специализация шаблона](../cpp/template-specialization-cpp.md)   
 [Практическое руководство. Преобразование различных типов строк](../text/how-to-convert-between-various-string-types.md)


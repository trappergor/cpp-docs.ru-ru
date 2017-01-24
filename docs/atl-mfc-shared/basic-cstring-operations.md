---
title: "Basic CString Operations | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "знаки, accessing in CStrings"
  - "CString objects"
  - "CString objects, основные операции"
  - "literal strings, CString operations"
  - "сравнение строк, CString operations"
  - "строковые литералы, CString operations"
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Basic CString Operations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются следующие основные операции [CString](../atl-mfc-shared/reference/cstringt-class.md):  
  
-   [Создание CString возражает из стандартных строк литералов C\#](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
-   [Доступ к отдельным знакам в CString](#_core_accessing_individual_characters_in_a_cstring)  
  
-   [Сцепить 2 объекта CString](#_core_concatenating_two_cstring_objects)  
  
-   [Сравнение объектов CString](#_core_comparing_cstring_objects)  
  
-   [Преобразование объектов CString](#_core_converting_cstring_objects)  
  
 `Class CString` основан на шаблоне [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) класса.  `CString``typedef``CStringT`.  Точнее, `CString``typedef`*явной специализации*`CStringT`, распространенный способ использовать шаблон класса для определения класса.  Аналогично, определенные классы `CStringA` и `CStringW`.  Дополнительные сведения о явной специализации см. в разделе [Создание экземпляра шаблона классов](../Topic/Class%20Template%20Instantiation.md).  
  
 `CString`, `CStringA` и `CStringW` определены в atlstr.h.  `CStringT` определено в cstringt.h.  
  
 `CString`, `CStringA` и `CStringW` получает набор методов и операторов, указанный `CStringT` для использования с данными строки.  Повторяющиеся некоторые из методов, а в некоторых случаях перегоняет службы строки библиотек времени выполнения c.  
  
 Примечание. `CString` собственный класс.  Для класса строки, для использования в проекте c управляемым \+\+\/CLI, используйте `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Создание объектов CString из стандартных строк литералов C\#  
 Можно присвоить C стилю строковые литералы в `CString` как можно присвоить один объект `CString` в другой.  
  
-   Присвойте значение строки c литеральной к объекту `CString`.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_1.cpp)]  
  
-   Присвойте значение одного `CString` другому объекту `CString`.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_2.cpp)]  
  
     Содержимое объекта `CString` копируются когда один объект `CString` присвоено другому.  Следовательно, 2 строк не используют ссылка на фактическое символы, составляющие строку.  Дополнительные сведения о том, как использовать объекты `CString` в качестве значений см. в разделе [CString Semantics](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  Написать приложение, чтобы оно может компилировать для Юникода или ANSI, строки кода литералы с помощью макроса \_T.  Дополнительные сведения см. в разделе [Поддержка Юникода и многобайтовой кодировки](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Доступ к отдельным знакам в CString  
 Можно получить доступ к отдельным знакам в объекте `CString` с помощью методов `GetAt` и `SetAt`.  Можно также использовать элемент массива или индекс, оператор \(\[\]\) вместо `GetAt` для получения отдельных символов.  \(Это напоминает доступа к элементам массива индексом, как в стандартных строк в стиле языка C\). Значения индекса для символов `CString` нулевой\- основаны.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> Сцепить 2 объекта CString  
 Для сцепления 2 объекта `CString`, используйте операторы объединения \(\+ или \+\=\) следующим образом.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_3.cpp)]  
  
 По крайней мере один аргумент до операторов объединения \(\+ или \+\=\), должен быть объектом `CString`, но может использовать константу собой строку символов \(например, `"big"`\) или `char` \(например, "x"\) для другого аргумента.  
  
##  <a name="_core_comparing_cstring_objects"></a> Сравнение объектов CString  
 Метод `Compare` и оператор \=\= для `CString` эквивалентны.  `Compare`, `operator==` и `CompareNoCase` и многобайтовая кодировка Юникод осведомленные; `CompareNoCase` также обращение\-нечувствительно.  Метод `Collate``CString` языковой стандарт\- важна и часто медленнее, чем `Compare`.  Используйте `Collate` только тогда, когда необходимо оставаться неизменным правилами сортировки, определенное текущим языковым стандартом.  
  
 В следующей таблице перечислены доступные функции сравнения [CString](../atl-mfc-shared/reference/cstringt-class.md) и их функции MBCS\-portable цифры Юникод Или в библиотеке времени выполнения языка c.  
  
|Функция CString|Функции многобайтовой кодировки|Функция Юникода|  
|---------------------|-------------------------------------|---------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 Шаблон класса `CStringT` определяет реляционные операторы \(\<, \<\=, \>\=, \>, \=\= и\! \=\), который доступен для использования `CString`.  Можно сравнить 2 `CStrings` с использованием этих операторов, как показано в следующем примере.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> Преобразование объектов CString  
 Дополнительные сведения о преобразовании CString возражает в строки других типов см. в разделе [Практическое руководство. Преобразование различных типов строк](../Topic/How%20to:%20Convert%20Between%20Various%20String%20Types.md).  
  
## Использование с wcout CString  
 Для использования CString с `wcout` необходимо явно привести объект в `const wchar_t*` как показано в следующем примере:  
  
```  
CString cs("meow");  
  wcout << (const wchar_t*) cs << endl;  
  
```  
  
 Без приведения, `cs` обрабатывается как `void*` и `wcout` введите адрес объекта.  Эта функциональности вызвана заметно взаимодействиями между вычетом аргумента шаблона и разрешение перегрузки, в себя верных и conformant с стандартом C\+\+.  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [Создание экземпляра шаблона классов](../Topic/Class%20Template%20Instantiation.md)   
 [Явная специализация шаблонов класса](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)   
 [Частичная специализация шаблонов класса](../cpp/template-specialization-cpp.md)   
 [Практическое руководство. Преобразование различных типов строк](../Topic/How%20to:%20Convert%20Between%20Various%20String%20Types.md)
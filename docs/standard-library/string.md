---
title: "&lt;string&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<string>"
  - "string/std::<string>"
  - "std.<string>"
  - "<string>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string - заголовок"
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;string&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс шаблонов контейнеров `basic_string` и некоторые вспомогательные шаблоны.  
  
 Для получения дополнительных сведений о `basic_string` см. [Класс basic\_string](../standard-library/basic-string-class.md)  
  
## Синтаксис  
  
```  
#include <string>  
```  
  
## Заметки  
 Язык C\+\+ и библиотека Standard C\+\+ поддерживают два типа строк:  
  
-   Массивы символов, оканчивающиеся нулевым символов, часто называют строками C.  
  
-   Объекты класса шаблонов типа `basic_string`, обрабатывающие все аргументы шаблонов, подобные `char`.  
  
### Определения типов  
  
|||  
|-|-|  
|[string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)|Тип, описывающий специализацию класса шаблона `basic_string` элементами типа `char` как `string`.|  
|[wstring](../Topic/wstring.md)|Тип, описывающий специализацию класса шаблона `basic_string` элементами типа `wchar_t` как `wstring`.|  
|[u16string](../Topic/u16string.md)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char16_t`.|  
|[u32string](../Topic/u32string.md)|Тип, описывающий специализацию класса шаблона `basic_string` на основе элементов типа `char32_t`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \+](../Topic/operator+%20\(%3Cstring%3E\).md)|Сцепляет два строковых объекта.|  
|[operator\!\=](../Topic/operator!=%20\(%3Cstring%3E\).md)|Проверяет, что строковый объект слева от оператора не равен строковому объекту справа от оператора.|  
|[operator\=\=](../Topic/operator==%20\(%3Cstring%3E\).md)|Проверяет, равен ли строковый объект слева от оператора строковому объекту справа от оператора.|  
|[Оператор \<](../Topic/operator%3C%20\(%3Cstring%3E\).md)|Проверяет, что строковый объект слева от оператора меньше строкового объекта справа от оператора.|  
|[Оператор \<\=](../Topic/operator%3C=%20\(in%20%3Cstring%3E\).md)|Проверяет, что строковый объект слева от оператора меньше или равен строковому объекту справа от оператора.|  
|[\<\< \- оператор](../Topic/operator%3C%3C%20\(%3Cstring%3E\).md)|Функция шаблона, вставляющая строку в выходной поток.|  
|[Оператор \>](../Topic/operator%3E%20\(%3Cstring%3E\).md)|Проверяет, что строковый объект слева от оператора больше строкового объекта справа от оператора.|  
|[Оператор \>\=](../Topic/operator%3E=%20\(%3Cstring%3E\).md)|Проверяет, что строковый объект слева от оператора больше или равен строковому объекту справа от оператора.|  
|[\>\> \- оператор](../Topic/operator%3E%3E%20\(%3Cstring%3E\).md)|Функция шаблона, извлекающая строку из входного потока.|  
  
### Специализированные функции шаблонов  
  
|||  
|-|-|  
|[буфер обмена](../Topic/swap%20\(C++%20STL%20%3Cstring%3E\).md)|Меняет местами массивы символов двух строк.|  
|[stod](../Topic/stod.md)|Преобразует последовательность символов в `double.`|  
|[stof](../Topic/stof.md)|Преобразует последовательность символов в `float`.|  
|[stoi](../Topic/stoi.md)|Преобразует последовательность символов в целое число.|  
|[stold](../Topic/stold.md)|Преобразует последовательность символов в `long double`.|  
|[stoll](../Topic/stoll.md)|Преобразует последовательность символов в `long long`.|  
|[stoul](../Topic/stoul.md)|Преобразует последовательность символов в `unsigned long`.|  
|[stoull](../Topic/stoull.md)|Преобразует последовательность символов в `unsigned long long`.|  
|[to\_string](../Topic/to_string.md)|Преобразует значение в `string`.|  
|[to\_wstring](../Topic/to_wstring.md)|Преобразует значение в двухбайтовое `string`.|  
  
### Функции  
  
|||  
|-|-|  
|[getline](../Topic/getline%20Template%20Function.md)|Извлекает строки из входного потока, последовательно по одной строке.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс basic\_string](../standard-library/basic-string-class.md)|Класс шаблона, описывающий объекты, которые могут хранить последовательность произвольных символьных объектов.|  
|[Структура char\_traits](../standard-library/char-traits-struct.md)|Класс шаблона, описывающий атрибуты, связанные с символом типа CharType|  
  
### Специализации  
  
|||  
|-|-|  
|[Структура char\_traits\<char\>](../standard-library/char-traits-char-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType\> к элементу типа `char`.|  
|[Структура char\_traits\<wchar\_t\>](../standard-library/char-traits-wchar-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType\> к элементу типа `wchar_t`.|  
|[Структура char\_traits\<char16\_t\>](../standard-library/char-traits-char16-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType\> к элементу типа `char16_t`.|  
|[Структура char\_traits\<char32\_t\>](../standard-library/char-traits-char32-t-struct.md)|Структура, которая является специализацией структуры шаблона `char_traits`\<CharType\> к элементу типа `char32_t`.|  
  
## Требования  
  
-   **Заголовок:** \<string\>  
  
-   **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)
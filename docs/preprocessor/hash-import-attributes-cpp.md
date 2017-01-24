---
title: "Атрибуты #import (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import - директива, атрибуты"
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Атрибуты #import (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предоставляет ссылки на атрибуты, используемые с директивой \#import.  
  
 **Блок, относящийся только к системам Microsoft**  
  
 Для директивы \#import доступны следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[auto\_rename](../preprocessor/auto-rename.md)|Переименовывает зарезервированные слова C\+\+ путем добавления двух знаков подчеркивания \(\_\_\) к именам переменных, чтобы разрешить потенциальные конфликты имен.|  
|[auto\_search](../preprocessor/auto-search.md)|Указывает, что если на библиотеку типов ссылаются при помощи директивы \#import, и при этом она сама ссылается на другую библиотеку типов, то компилятор может неявным образом выполнить директиву \#import и для второй библиотеки типов.|  
|[embedded\_idl](../preprocessor/embedded-idl.md)|Указывает, что библиотека типов записывается в файл .tlh с сохранением кода, созданного с атрибутами.|  
|[exclude](../preprocessor/exclude-hash-import.md)|Исключает элементы из создаваемых файлов заголовка библиотеки типов.|  
|[high\_method\_prefix](../preprocessor/high-method-prefix.md)|Задает префикс, используемый при именовании высокоуровневых свойств и методов.|  
|[high\_property\_prefixes](../Topic/high_property_prefixes.md)|Задает другие префиксы для трех методов свойств.|  
|[implementation\_only](../preprocessor/implementation-only.md)|Отключает создание файла заголовка .tlh \(основного файла заголовка\).|  
|[include\(\)](../preprocessor/include-parens.md)|Отключает автоматическое исключение.|  
|[inject\_statement](../preprocessor/inject-statement.md)|Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.|  
|[named\_guids](../preprocessor/named-guids.md)|Указывает компилятору определять и инициализировать переменные GUID в старом стиле, в форме **LIBID\_MyLib**, **CLSID\_MyCoClass**, **IID\_MyInterface** и **DIID\_MyDispInterface**.|  
|[no\_auto\_exclude](../preprocessor/no-auto-exclude.md)|Отключает автоматическое исключение.|  
|[no\_dual\_interfaces](../preprocessor/no-dual-interfaces.md)|Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.|  
|[no\_implementation](../preprocessor/no-implementation.md)|Отключает создание заголовка .tli, который содержит реализацию функций\-членов оболочки.|  
|[no\_namespace](../Topic/no_namespace.md)|Указывает, что пространство имен не генерируется компилятором.|  
|[no\_registry](../Topic/no_registry.md)|Указывает компилятору не искать библиотеки типов в реестре.|  
|[no\_search\_namespace](../preprocessor/no-search-namespace.md)|Имеет ту же функцию, что и атрибут [no\_namespace](../Topic/no_namespace.md), однако применяется для библиотек типов, для которых вы использовали директиву \#import с атрибутом [auto\_search](../preprocessor/auto-search.md).|  
|[no\_smart\_pointers](../preprocessor/no-smart-pointers.md)|Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.|  
|[raw\_dispinterfaces](../Topic/raw_dispinterfaces.md)|Указывает компилятору сгенерировать низкоуровневые функции оболочки для методов и свойств disp\-интерфейса, а также свойства, которые вызывают функцию **IDispatch::Invoke** и возвращают код ошибки `HRESULT`.|  
|[raw\_interfaces\_only](../Topic/raw_interfaces_only.md)|Отключает создание функций оболочки обработки ошибок, а также объявлений [property](../cpp/property-cpp.md), в которых используются такие функции оболочки.|  
|[raw\_method\_prefix](../preprocessor/raw-method-prefix.md)|Указывает другой префикс, чтобы избежать конфликтов имен.|  
|[raw\_native\_types](../Topic/raw_native_types.md)|Отключает использование классов поддержки COM в высокоуровневых функциях оболочки и принудительно использует вместо них низкоуровневые типы данных.|  
|[raw\_property\_prefixes](../preprocessor/raw-property-prefixes.md)|Задает другие префиксы для трех методов свойств.|  
|[переименовать](../preprocessor/rename-hash-import.md)|Обходит проблемы конфликтов имен.|  
|[rename\_namespace](../preprocessor/rename-namespace.md)|Переименовывает пространство имен, к которому относится содержимое библиотеки типов.|  
|[rename\_search\_namespace](../preprocessor/rename-search-namespace.md)|Имеет ту же функцию, что и атрибут [rename\_namespace](../preprocessor/rename-namespace.md), однако применяется для библиотек типов, для которых вы использовали директиву \#import с атрибутом [auto\_search](../preprocessor/auto-search.md).|  
|[tlbid](../preprocessor/tlbid.md)|Позволяет загружать библиотеки, отличные от основной библиотеки типов.|  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)
---
title: "&lt;system_error&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<system_error>"
  - "std::<system_error>"
  - "<system_error>"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error - заголовок"
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;system_error&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включать заголовок `<system_error>` для определения класса исключений `system_error` и соответствующие шаблоны для обработки низкоуровневые системные ошибки.  
  
## Синтаксис  
  
```  
#include <system_error>  
```  
  
### Объекты  
  
|||  
|-|-|  
|[generic\_category](../Topic/generic_category.md)|Представляет категорию для универсальных ошибок.|  
|[system\_category](../Topic/system_category.md)|Представляет категорию для ошибок, вызванных низкоуровневыми переполнениями системы.|  
  
### Определения типов  
  
|||  
|-|-|  
|[generic\_errno](../Topic/generic_errno.md)|Тип, представляющий перечисление, предоставляет символические имена для всех макросов ошибка\- POSIX для кода, в `<errno.h>`.|  
  
### Функции  
  
|||  
|-|-|  
|[make\_error\_code](../Topic/make_error_code.md)|Создает объект `error_code`.|  
|[make\_error\_condition](../Topic/make_error_condition.md)|Создает объект `error_condition`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20\(%3Csystem_error%3E\).md)|Тесты, если объект в левой части оператора равно объекту в правой части.|  
|[operator\!\=](../Topic/operator!=%20\(%3Csystem_error%3E\).md)|Тесты, если объект в левой части оператора не равен объекту в правой части.|  
|[operator\<](../Topic/operator%3C%20\(%3Csystem_error%3E\).md)|Тесты, если объект не был передан в объект для сравнения.|  
  
### Перечисления  
  
|||  
|-|-|  
|[errc](../Topic/errc%20Enumeration.md)|Предоставляет символические имена для всех макросов, определенных в ошибка\- кода POSIX для `<errno.h>`.|  
  
### Классы и структуры  
  
|||  
|-|-|  
|[error\_category](../standard-library/error-category-class.md)|Представляет абстрактный базу, общего для объектов, которая описывает категорию кодов ошибок.|  
|[error\_code](../standard-library/error-code-class.md)|Представляет низкоуровневые системные ошибки, предоставления с.|  
|[error\_condition](../standard-library/error-condition-class.md)|Представляет определяемые пользователем коды ошибок.|  
|[is\_error\_code\_enum](../standard-library/is-error-code-enum-class.md)|Представляет предикат типа, тесты для перечисления [Класс error\_code](../standard-library/error-code-class.md).|  
|[is\_error\_condition\_enum](../standard-library/is-error-condition-enum-class.md)|Представляет предикат типа, тесты для перечисления [Класс error\_condition](../standard-library/error-condition-class.md).|  
|[system\_error](../standard-library/system-error-class.md)|Представляет базовый класс для всех исключений, чтобы уведомить являются переполнение системы.|  
  
## Требования  
 **Заголовок:**\<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
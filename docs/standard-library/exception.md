---
title: "&lt;exception&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<exception>"
  - "std::<exception>"
  - "std.<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception - заголовок"
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;exception&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет несколько типов и функций, связанных с обработкой исключений. Обработка исключений используется в ситуациях, когда система может восстановиться после ошибки. Она предоставляет средства для возврата управления из функции в программу. Целью внедрения обработки исключений является повышение надежности программы с одновременным обеспечением возможности восстановления после ошибки определенным образом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[exception_ptr](../Topic/%3Cexception%3E%20typedefs.md#exception_ptr)|Тип, который описывает указатель на исключение.|  
|[terminate_handler](../Topic/%3Cexception%3E%20typedefs.md#terminate_handler)|Тип, который описывает указатель на функцию, подходящую для использования в качестве `terminate_handler`.|  
|[unexpected_handler](../Topic/%3Cexception%3E%20typedefs.md#unexpected_handler)|Тип, который описывает указатель на функцию, подходящую для использования в качестве `unexpected_handler`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[current_exception](../Topic/%3Cexception%3E%20functions.md#current_exception)|Получает указатель на текущее исключение.|  
|[get_terminate](../Topic/%3Cexception%3E%20functions.md#get_terminate)|Получает текущую функцию `terminate_handler`.|  
|[get_unexpected](../Topic/%3Cexception%3E%20functions.md#get_unexpected)|Получает текущую функцию `unexpected_handler`.|  
|[make_exception_ptr](../Topic/%3Cexception%3E%20functions.md#make_exception_ptr)|Создает объект `exception_ptr`, содержащий копию исключения.|  
|[rethrow_exception](../Topic/%3Cexception%3E%20functions.md#rethrow_exception)|Создает исключение, переданное в качестве параметра.|  
|[set_terminate](../Topic/%3Cexception%3E%20functions.md#set_terminate)|Создает новый `terminate_handler`, подлежащий вызову при завершении программы.|  
|[set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected)|Создает новый `unexpected_handler`, подлежащий вызову при обнаружении неожиданного исключения.|  
|[завершить](../Topic/%3Cexception%3E%20functions.md#terminate)|Вызывает обработчик завершения.|  
|[uncaught_exception](../Topic/%3Cexception%3E%20functions.md#uncaught_exception)|Возвращает **значение true,** только в том случае, если созданное исключение в настоящий момент обрабатывается.|  
|[Непредвиденная](../Topic/%3Cexception%3E%20functions.md#unexpected)|Вызывает непредвиденный обработчик.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс bad_exception](../standard-library/bad-exception-class.md)|Этот класс описывает исключение, которое можно вызывать из `unexpected_handler`.|  
|[Класс Exception](Exception%20Class.xml)|Этот класс служит базовым классом для всех исключений, создаваемых определенными выражениями и стандартной библиотекой C++.|  
  
## <a name="see-also"></a>См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


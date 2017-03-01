---
title: "&lt;exception&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <exception>
- std::<exception>
- std.<exception>
dev_langs:
- C++
helpviewer_keywords:
- exception header
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 1d4ccc904c1f6011231e668194a9d84499fee934
ms.lasthandoff: 02/24/2017

---
# <a name="ltexceptiongt"></a>&lt;exception&gt;
Определяет несколько типов и функций, связанных с обработкой исключений. Обработка исключений используется в ситуациях, когда система может восстановиться после ошибки. Она предоставляет средства для возврата управления из функции в программу. Целью внедрения обработки исключений является повышение надежности программы с одновременным обеспечением возможности восстановления после ошибки определенным образом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)|Тип, который описывает указатель на исключение.|  
|[terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)|Тип, который описывает указатель на функцию, подходящую для использования в качестве `terminate_handler`.|  
|[unexpected_handler](../standard-library/exception-typedefs.md#unexpected_handler)|Тип, который описывает указатель на функцию, подходящую для использования в качестве `unexpected_handler`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[current_exception](../standard-library/exception-functions.md#current_exception)|Получает указатель на текущее исключение.|  
|[get_terminate](../standard-library/exception-functions.md#get_terminate)|Получает текущую функцию `terminate_handler`.|  
|[get_unexpected](../standard-library/exception-functions.md#get_unexpected)|Получает текущую функцию `unexpected_handler`.|  
|[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)|Создает объект `exception_ptr`, содержащий копию исключения.|  
|[rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)|Создает исключение, переданное в качестве параметра.|  
|[set_terminate](../standard-library/exception-functions.md#set_terminate)|Создает новый `terminate_handler`, подлежащий вызову при завершении программы.|  
|[set_unexpected](../standard-library/exception-functions.md#set_unexpected)|Создает новый `unexpected_handler`, подлежащий вызову при обнаружении неожиданного исключения.|  
|[terminate](../standard-library/exception-functions.md#terminate)|Вызывает обработчик завершения.|  
|[uncaught_exception](../standard-library/exception-functions.md#uncaught_exception)|Возвращает **true**, только если созданное исключение в настоящий момент обрабатывается.|  
|[unexpected](../standard-library/exception-functions.md#unexpected)|Вызывает непредвиденный обработчик.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс bad_exception](../standard-library/bad-exception-class.md)|Этот класс описывает исключение, которое можно вызывать из `unexpected_handler`.|  
|[Класс exception](../standard-library/exception-class.md)|Этот класс служит базовым классом для всех исключений, создаваемых определенными выражениями и стандартной библиотекой C++.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



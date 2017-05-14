---
title: "&lt;new&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<new>
- <new>
- std.<new>
dev_langs:
- C++
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: e804f35db459c7fe50bb36fa8eeaf795d04cc621
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltnewgt"></a>&lt;new&gt;
Определяет несколько функций и типов, управляющих выделением и освобождением памяти, которая находится под управлением программы. Он также определяет компоненты для создания отчетов об ошибках управления хранилищем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <new>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Некоторые функции, объявленные в этом заголовке, можно заменить. Данная реализация предоставляет версию по умолчанию, поведение которой описано в этом документе. Однако программа может определить функцию с той же самой сигнатурой, чтобы заменить версию по умолчанию во время компоновки. Версия, на которую производится замена, должна удовлетворять требованиям, описанным в этом документе.  
  
### <a name="objects"></a>Объекты  
  
|||  
|-|-|  
|[nothrow](../standard-library/new-functions.md#nothrow)|Предоставляет объект для использования в качестве аргумента для `nothrow` версий **new** и **delete**.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[new_handler](../standard-library/new-typedefs.md#new_handler)|Тип, который указывает на функцию, подходящую для использования в качестве нового обработчика.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|Устанавливает пользовательскую функцию, вызываемую в случае сбоя оператора new при попытке выделения памяти.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор delete](../standard-library/new-operators.md#op_delete)|Функция, вызываемая с помощью выражения delete для отмены выделения хранилища для отдельных объектов.|  
|[оператор delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|Функция, вызываемая с помощью выражения delete для отмены выделения хранилища для массива объектов.|  
|[оператор new](../standard-library/new-operators.md#op_new)|Функция, вызываемая с помощью выражения new для выделения хранилища для отдельных объектов.|  
|[оператор new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|Функция, вызываемая с помощью выражения new для выделения хранилища для массива объектов.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс bad_alloc](../standard-library/bad-alloc-class.md)|Данный класс описывает исключение, возникновение которого указывает на то, что запрос на выделение памяти не выполнен.|  
|[Класс nothrow_t](../standard-library/nothrow-t-structure.md)|Этот класс используется как параметр функции для оператора new, чтобы показать, что для указания на ошибку выделения данная функция должна возвращать пустой указатель (NULL), а не вызывать исключение.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





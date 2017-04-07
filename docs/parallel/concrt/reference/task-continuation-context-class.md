---
title: "Класс task_continuation_context | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8afd599e5ee489500d7f8c498d03c91ace6b99ed
ms.lasthandoff: 03/17/2017

---
# <a name="taskcontinuationcontext-class"></a>Класс task_continuation_context
Класс `task_continuation_context` позволяет указать место продолжения выполнения задачи. Этот класс рекомендуется использовать из приложения Магазина Windows. При использовании других приложений контекст выполнения продолжения задачи определяется средой выполнения и не настраивается.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока winrt.|  
|[use_arbitrary](#use_arbitrary)|Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.|  
|[use_current](#use_current)|Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.|  
|[use_default](#use_default)|Создает контекст продолжения задачи по умолчанию.|  
|[use_synchronous_execution](#use_synchronous_execution)|Возвращает объект контекста продолжения задачи, представляющий контекст выполнения синхронной.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  

## <a name="get_current_winrt_context"></a>get_current_winrt_context
 Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока WinRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Текущий контекст потока среды выполнения Windows. Возвращает пустой task_continuation_context при вызове из контекста выполнения Windows.  
  
## <a name="remarks"></a>Примечания  
 `get_current_winrt_context` Метод перехватывает контекст потока вызывающего среды выполнения Windows. Он возвращает контекст пустой вызывающим выполнения Windows.  
  
 Значение, возвращаемое `get_current_winrt_context` может использоваться для указания среды выполнения, что в потоковой модели записанный контекст (STA vs MTA), должно выполняться продолжение, независимо от того, предшествующей задачи учитывать подразделения. Подразделение учитывать задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи.  
  
 Этот метод аналогичен `use_current` метода, но он также может использоваться для машинного кода C++ не используется C + +/ CX поддержка расширения. Он предназначен для использования Опытные пользователи записи C + +/ CX независимой от кода библиотеки машинный код и вызывающие объекты среды выполнения Windows. Если эта функция необходима, мы не рекомендуем `use_current` метод, который доступен только на C + +/ CX клиентов.  
  
  
##  <a name="use_arbitrary"></a>use_arbitrary 

 Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекст продолжения задачи, представляющий произвольное место.  
  
### <a name="remarks"></a>Примечания  
 Когда используется этот контекст продолжения продолжение будет выполняться в контексте, который среда выполнения выбирает, даже если предшествующая задача является подразделением виду.  
  
 `use_arbitrary`можно использовать для отключения поведения по умолчанию для продолжения на задачу учитывать подразделения, созданные в однопотоковое подразделение.  
  
 Этот метод доступен только для приложений для магазина Windows.  
  
##  <a name="use_current"></a>use_current 

 Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает текущий контекст выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод записывает вызывающего контекста среды выполнения Windows, чтобы продолжения могут быть выполнены в подразделении справа.  
  
 Значение, возвращаемое `use_current` может использоваться для указания среды выполнения, что продолжение следует выполнять в захваченном контексте (STA или MTA) независимо от того, ли предшествующей задачи учитывать подразделения. Подразделение учитывать задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи.  
  
 Этот метод доступен только для приложений для магазина Windows.  
  
##  <a name="use_default"></a>use_default 

 Создает контекст продолжения задачи по умолчанию.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекст продолжения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Контекст по умолчанию используется в том случае, если вы не укажите контекст продолжения при вызове `then` метода. В приложениях Windows для Windows 7 и ниже, а также настольных приложений Windows 8 и более поздних версиях среда выполнения определяет, где будет выполняться продолжений задач. Тем не менее, в приложении для магазина Windows, контекст продолжения по умолчанию для продолжения в подразделении задач является подразделение где `then` вызывается.  
  
 Подразделение учитывать задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи. Таким образом Если запланировать продолжения в подразделении задач в STA среды выполнения Windows, продолжение будет выполняться в этом однопотоковое подразделение.  
  
 Продолжение не подразделения учитывать задачи будет выполняться в контексте, который среда выполнения выбирает.  

## <a name="use_synchronous_execution"></a>task_continuation_context::use_synchronous_execution  
Возвращает объект контекста продолжения задачи, представляющий контекст выполнения синхронной.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Контекст выполнения синхронной.  
  
## <a name="remarks"></a>Примечания  
 `use_synchronous_execution` Метод вынуждает одновременного выполнения в контексте приводит к завершения предшествующей задачи задача продолжения.  
  
 Если предшествующая задача уже завершена при присоединении продолжение, продолжение выполняется синхронно в контексте, который присоединяет продолжение.  
  
 
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)


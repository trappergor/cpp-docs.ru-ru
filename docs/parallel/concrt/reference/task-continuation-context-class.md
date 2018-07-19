---
title: Класс task_continuation_context | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37b218a6db251123513ca155fd491fee7ebabd13
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689185"
---
# <a name="taskcontinuationcontext-class"></a>Класс task_continuation_context
Класс `task_continuation_context` позволяет указать место продолжения выполнения задачи. Ключ используется только с помощью этого класса из приложения среды выполнения Windows. Для приложений Windows Runtime контекст выполнения продолжения задачи определяется средой выполнения и не настраивается.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока winrt.|  
|[use_arbitrary](#use_arbitrary)|Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.|  
|[use_current](#use_current)|Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.|  
|[use_default](#use_default)|Создает контекст продолжения задачи по умолчанию.|  
|[use_synchronous_execution](#use_synchronous_execution)|Возвращает объект контекста продолжения задачи, представляющий контекст синхронного выполнения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  

## <a name="get_current_winrt_context"></a> get_current_winrt_context
 Возвращает объект контекста продолжения задачи, представляющий текущий контекст потока WinRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Текущий контекст потока среды выполнения Windows. Возвращает пустой task_continuation_context при вызове из контекста выполнения Windows.  
  
## <a name="remarks"></a>Примечания  
 `get_current_winrt_context` Метод перехватывает контекст потока вызывающего среды выполнения Windows. Он возвращает пустой контекст выполнения Windows вызывающим объектам.  
  
 Значение, возвращаемое `get_current_winrt_context` может использоваться для указания на среду выполнения, в потоковой модели перехваченного контекста (STA и MTA), должно выполняться продолжение, независимо от того, предшествующая задача виду подразделения. Подразделение виду задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи.  
  
 Этот метод аналогичен `use_current` метода, но он также может использоваться для машинного кода C++ без C + +/ CX поддержки расширения. Он предназначен для использования в сложных пользователей записи C + +/ CX независимой от кода библиотеки машинный код и вызывающие объекты среды выполнения Windows. Если эта функция необходима, мы не рекомендуем `use_current` метод, который доступен только для C + +/ CX клиентов.  
  
  
##  <a name="use_arbitrary"></a> use_arbitrary 

 Создает контекст продолжения выполнения задачи, который позволяет среде выполнения возможность выбора контекста для продолжения.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекст продолжения задачи, представляющий произвольное расположение.  
  
### <a name="remarks"></a>Примечания  
 Если используется этот контекст продолжения продолжение будет выполняться в контексте, который среда выполнения выбирает, даже если предшествующая задача является подразделением виду.  
  
 `use_arbitrary` можно использовать для отключения поведения по умолчанию для продолжение подразделения виду задачи, созданные в однопотоковое подразделение.  
  
 Этот метод доступен только в приложениях среды выполнения Windows.  
  
##  <a name="use_current"></a> use_current 

 Возвращает объект контекста продолжения задачи, представляющий контекст текущего выполнения.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает текущий контекст выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод записывает контекста вызывающей среды выполнения Windows, продолжения можно использовать в подразделении вправо.  
  
 Значение, возвращаемое `use_current` может использоваться для указания на среду выполнения, продолжение должно выполняться в контексте записанного (STA и MTA), независимо от того, ли предшествующая задача является подразделением учитывать. Подразделение виду задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи.  
  
 Этот метод доступен только в приложениях среды выполнения Windows.  
  
##  <a name="use_default"></a> use_default 

 Создает контекст продолжения задачи по умолчанию.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекст продолжения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Используется контекст по умолчанию, если вы не укажите контекст продолжения, при вызове `then` метода. В приложениях Windows для Windows 7 и ниже, а также настольных приложений для Windows 8 и более поздних версиях среда выполнения определяет, где будет выполняться продолжений задач. Тем не менее, в приложении среды выполнения Windows, контекст продолжения по умолчанию для продолжения задачи виду подразделения с является подразделением где `then` вызывается.  
  
 Подразделение виду задача — это задача, которая распаковывает среды выполнения Windows `IAsyncInfo` интерфейса или задачу, которая является потомком такой задачи. Таким образом Если запланировать продолжение задачи виду подразделения в STA среды выполнения Windows, продолжение будет выполняться в этом однопотоковое подразделение.  
  
 Продолжение не подразделения виду задачи будет выполняться в контексте, который среда выполнения выбирает.  

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution  
Возвращает объект контекста продолжения задачи, представляющий контекст синхронного выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Контекст синхронного выполнения.  
  
## <a name="remarks"></a>Примечания  
 `use_synchronous_execution` Метод принудительно для синхронного выполнения в контексте, причиной завершения предшествующей задачи задача продолжения.  
  
 Если предшествующая задача уже завершена при присоединении продолжения, продолжение выполняется синхронно в контексте, который присоединяет продолжения.  
  
 
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

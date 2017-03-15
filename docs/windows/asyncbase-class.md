---
title: "Класс AsyncBase | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncBase - класс"
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Класс AsyncBase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализует асинхронный конечный автомат среды выполнения Windows.  
  
## Синтаксис  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### Параметры  
 `TComplete`  
 Обработчик событий, вызываемый при завершении асинхронной операции.  
  
 `TProgress`  
 Обработчик событий, вызываемый, когда асинхронная операция хода сообщает о текущем ходе выполнения операции.  
  
 `resultType`  
 Одно из значений перечисления [AsyncResultType](../windows/asyncresulttype-enumeration.md).  SingleResult, по умолчанию.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор AsyncBase::AsyncBase](../windows/asyncbase-asyncbase-constructor.md)|Инициализирует экземпляр класса AsyncBase.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод AsyncBase::Cancel](../Topic/AsyncBase::Cancel%20Method.md)|Отменяет асинхронную операцию.|  
|[Метод AsyncBase::Close](../windows/asyncbase-close-method.md)|Закрывает асинхронную операцию.|  
|[Метод AsyncBase::FireCompletion](../windows/asyncbase-firecompletion-method.md)|Вызывает обработчик событий завершения или сбрасывает внутренний делегат выполнения.|  
|[Метод AsyncBase::FireProgress](../windows/asyncbase-fireprogress-method.md)|Вызывает текущий прогресс обработчика событий.|  
|[Метод AsyncBase::get\_ErrorCode](../windows/asyncbase-get-errorcode-method.md)|Получает код ошибки для текущей асинхронной операции.|  
|[Метод AsyncBase::get\_Id](../windows/asyncbase-get-id-method.md)|Извлекает дескриптор асинхронной операции.|  
|[Метод AsyncBase::get\_Status](../Topic/AsyncBase::get_Status%20Method.md)|Извлекает значение, обозначающее состояние асинхронной операции.|  
|[Метод AsyncBase::GetOnComplete](../windows/asyncbase-getoncomplete-method.md)|Копирует адрес текущего обработчика событий завершения в указанную переменную.|  
|[Метод AsyncBase::GetOnProgress](../windows/asyncbase-getonprogress-method.md)|Копирует адрес текущего прогресса обработчика событий завершения в указанную переменную.|  
|[Метод AsyncBase::put\_Id](../windows/asyncbase-put-id-method.md)|Устанавливает дескриптор асинхронной операции.|  
|[Метод AsyncBase::PutOnComplete](../windows/asyncbase-putoncomplete-method.md)|Задает адрес обработчика события завершения в указанное значение.|  
|[Метод AsyncBase::PutOnProgress](../windows/asyncbase-putonprogress-method.md)|Задает адрес обработчика событий хода выполнения.|  
|[Метод AsyncBase::Start](../windows/asyncbase-start-method.md)|Запускает асинхронную операцию.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод AsyncBase::CheckValidStateForDelegateCall](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Проверяет, можно ли изменить свойства делегата в текущем асинхронном состоянии.|  
|[Метод AsyncBase::CheckValidStateForResultsCall](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Проверяет, можно ли собрать результаты асинхронной операции в текущем асинхронном состоянии.|  
|[Метод AsyncBase::ContinueAsyncOperation](../Topic/AsyncBase::ContinueAsyncOperation%20Method.md)|Указывает, следует ли продолжить или остановить операцию асинхронной обработки.|  
|[Метод AsyncBase::CurrentStatus](../Topic/AsyncBase::CurrentStatus%20Method.md)|Извлекает состояние текущей асинхронной операции.|  
|[Метод AsyncBase::ErrorCode](../windows/asyncbase-errorcode-method.md)|Получает код ошибки для текущей асинхронной операции.|  
|[Метод AsyncBase::OnCancel](../windows/asyncbase-oncancel-method.md)|При переопределении в производном классе отменяет асинхронную операцию.|  
|[Метод AsyncBase::OnClose](../windows/asyncbase-onclose-method.md)|При переопределении в производном классе закрывает асинхронную операцию.|  
|[Метод AsyncBase::OnStart](../windows/asyncbase-onstart-method.md)|При переопределении в производном классе, начинает асинхронную операцию.|  
|[Метод AsyncBase::TryTransitionToCompleted](../windows/asyncbase-trytransitiontocompleted-method.md)|Показывает, выполнена ли текущая асинхронная операция.|  
|[Метод AsyncBase::TryTransitionToError](../windows/asyncbase-trytransitiontoerror-method.md)|Указывает, может ли указанный код ошибки изменить состояние внутренней ошибки.|  
  
## Иерархия наследования  
 `AsyncBase`  
  
 `AsyncBase`  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
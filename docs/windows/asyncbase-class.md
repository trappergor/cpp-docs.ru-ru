---
title: Класс AsyncBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
dev_langs:
- C++
helpviewer_keywords:
- AsyncBase class
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dcf5a095167e48a52405978a105cadaddfa870f2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647818"
---
# <a name="asyncbase-class"></a>AsyncBase - класс
Реализует асинхронный конечный автомат среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase<TComplete, Details::Nil, resultType> : public Microsoft::WRL::Implements<IAsyncInfo>;  
```  
  
### <a name="parameters"></a>Параметры  
 *TComplete*  
 Обработчик событий, вызываемый при завершении асинхронной операции.  
  
 *TProgress*  
 Обработчик событий, вызываемый при асинхронной операции отображается ход выполнения текущей операции.  
  
 *Тип resultType*  
 Один из [AsyncResultType](../windows/asyncresulttype-enumeration.md) значений перечисления. По умолчанию `SingleResult`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор AsyncBase::AsyncBase](../windows/asyncbase-asyncbase-constructor.md)|Инициализирует новый экземпляр класса **AsyncBase** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод AsyncBase::Cancel](../windows/asyncbase-cancel-method.md)|Отменяет асинхронную операцию.|  
|[Метод AsyncBase::Close](../windows/asyncbase-close-method.md)|Закрывает асинхронной операции.|  
|[Метод AsyncBase::FireCompletion](../windows/asyncbase-firecompletion-method.md)|Вызывает обработчик события завершения или сбрасывает делегат внутренней хода выполнения.|  
|[Метод AsyncBase::FireProgress](../windows/asyncbase-fireprogress-method.md)|Вызывает текущий обработчик событий процесса выполнения.|  
|[Метод AsyncBase::get_ErrorCode](../windows/asyncbase-get-errorcode-method.md)|Получает код ошибки для текущей асинхронной операции.|  
|[Метод AsyncBase::get_Id](../windows/asyncbase-get-id-method.md)|Извлекает дескриптор асинхронной операции.|  
|[Метод AsyncBase::get_Status](../windows/asyncbase-get-status-method.md)|Получает значение, указывающее состояние асинхронной операции.|  
|[Метод AsyncBase::GetOnComplete](../windows/asyncbase-getoncomplete-method.md)|Копирует адрес текущего обработчика событий завершения в указанной переменной.|  
|[Метод AsyncBase::GetOnProgress](../windows/asyncbase-getonprogress-method.md)|Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.|  
|[Метод AsyncBase::put_Id](../windows/asyncbase-put-id-method.md)|Задает дескриптор асинхронной операции.|  
|[Метод AsyncBase::PutOnComplete](../windows/asyncbase-putoncomplete-method.md)|Задает адрес обработчик события завершения для указанного значения.|  
|[Метод AsyncBase::PutOnProgress](../windows/asyncbase-putonprogress-method.md)|Задает адрес обработчика событий процесса выполнения указанное значение.|  
|[Метод AsyncBase::Start](../windows/asyncbase-start-method.md)|Начинает асинхронную операцию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод AsyncBase::CheckValidStateForDelegateCall](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Проверяет, является ли делегат свойства можно изменить в текущем состоянии асинхронной.|  
|[Метод AsyncBase::CheckValidStateForResultsCall](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Проверяет, является ли результаты асинхронной операции можно собирать в текущем состоянии асинхронной.|  
|[Метод AsyncBase::ContinueAsyncOperation](../windows/asyncbase-continueasyncoperation-method.md)|Определяет, должны продолжать обработку асинхронной операции или следует остановить.|  
|[Метод AsyncBase::CurrentStatus](../windows/asyncbase-currentstatus-method.md)|Извлекает состояние текущей асинхронной операции.|  
|[Метод AsyncBase::ErrorCode](../windows/asyncbase-errorcode-method.md)|Получает код ошибки для текущей асинхронной операции.|  
|[Метод AsyncBase::OnCancel](../windows/asyncbase-oncancel-method.md)|При переопределении в производном классе отменяет асинхронную операцию.|  
|[Метод AsyncBase::OnClose](../windows/asyncbase-onclose-method.md)|При переопределении в производном классе, закрывает асинхронной операции.|  
|[Метод AsyncBase::OnStart](../windows/asyncbase-onstart-method.md)|При переопределении в производном классе запускает асинхронную операцию.|  
|[Метод AsyncBase::TryTransitionToCompleted](../windows/asyncbase-trytransitiontocompleted-method.md)|Указывает, завершена ли текущей асинхронной операции.|  
|[Метод AsyncBase::TryTransitionToError](../windows/asyncbase-trytransitiontoerror-method.md)|Указывает, является ли указанный код ошибки можно изменить внутреннее состояние ошибки.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `AsyncBase`  
  
 `AsyncBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
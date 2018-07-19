---
title: Структура InvokeHelper | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper structure
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b612530c1a29588cd837b2cdbeef37faf84c8b4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880411"
---
# <a name="invokehelper-structure"></a>InvokeHelper - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback,  
   unsigned int argCount  
>  
struct InvokeHelper;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 0> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 1> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 2> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 3> : public Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 4> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 5> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 6> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 7> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 8> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
struct InvokeHelper<TDelegateInterface, TCallback, 9> : Microsoft::WRL::RuntimeClass<RuntimeClassFlags<Delegate>, TDelegateInterface>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `TDelegateInterface`  
 `TCallback`  
 Тип функции обработчика событий.  
  
 `argCount`  
 Число аргументов в специализации InvokeHelper.  
  
## <a name="remarks"></a>Примечания  
 Предоставляет реализацию на основе заданного числа и тип аргументов метода Invoke().  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Traits`|Синоним для класса, который определяет тип каждого аргумента обработчика событий.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор InvokeHelper::InvokeHelper](../windows/invokehelper-invokehelper-constructor.md)|Инициализирует новый экземпляр класса InvokeHelper.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод InvokeHelper::Invoke](../windows/invokehelper-invoke-method.md)|Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных InvokeHelper::callback_](../windows/invokehelper-callback-data-member.md)|Представляет обработчик событий вызывается при возникновении события.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `InvokeHelper`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)
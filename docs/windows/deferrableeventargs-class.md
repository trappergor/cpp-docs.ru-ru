---
title: Класс DeferrableEventArgs | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 15be5c26e5d4e976eaba7b6b24e1bf4f62c53aca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="deferrableeventargs-class"></a>Класс DeferrableEventArgs
Класс шаблона, используемый для типов аргументов событий для задержек.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `TEventArgsInterface`  
 Тип интерфейса, который объявляет аргументы для отложенного события.  
  
 `TEventArgsClass`  
 Класс, который реализует `TEventArgsInterface`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод DeferrableEventArgs::GetDeferral](../windows/deferrableeventargs-getdeferral-method.md)|Возвращает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.|  
|[Метод DeferrableEventArgs::InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md)|Вызывается, чтобы указать, что вся обработка для отложенного события завершена.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляры этого класса передаются в обработчики событий для отложенных событий. Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.  
  
 Класс отображается как первый аргумент обработчика событий для отложенного события. Можно вызвать [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) метод, чтобы получить [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объекта, из которого можно получить все сведения об отложенном событии. После завершения обработки событий необходимо вызвать завершение в объекте «Задержка». Затем следует вызвать [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) в конце метода обработчика событий, который гарантирует завершение всех отложенных событий будут передаваться должным образом.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
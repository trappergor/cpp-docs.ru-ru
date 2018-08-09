---
title: Класс DeferrableEventArgs | Документация Майкрософт
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
ms.openlocfilehash: 8dd9452133267021effd307734b5c5cf55922720
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642306"
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
  
### <a name="parameters"></a>Параметры  
 *TEventArgsInterface*  
 Тип интерфейса, который объявляет аргументы для отложенного события.  
  
 *TEventArgsClass*  
 Класс, реализующий *TEventArgsInterface*.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод DeferrableEventArgs::GetDeferral](../windows/deferrableeventargs-getdeferral-method.md)|Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.|  
|[Метод DeferrableEventArgs::InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md)|Вызывается, чтобы указать, что вся обработка для отложенного события завершена.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляры этого класса передаются в обработчики событий для отложенных событий. Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.  
  
 Класс отображается как первый аргумент обработчика событий для отложенного события. Можно вызвать [задержка](../windows/deferrableeventargs-getdeferral-method.md) метод для получения [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, из которого можно получить все сведения об отложенном событии. После завершения обработки событий необходимо вызвать завершение в объекте «Задержка». Затем следует вызвать [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) в конце метода обработчика событий, который гарантирует, что завершение всех отложенных событий передается надлежащим образом.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
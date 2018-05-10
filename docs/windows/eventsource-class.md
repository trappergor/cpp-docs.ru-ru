---
title: Класс EventSource | Документы Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b2d466b317927cd8de259637450b68b6aaf13bd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="eventsource-class"></a>EventSource - класс
Представляет событие, отличный от agile. Функции-члены EventSource добавлять, удалять и вызывать обработчики событий. Agile события используйте [AgileEventSource](agileeventsource-class.md). 
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
#### <a name="parameters"></a>Параметры  
 `TDelegateInterface`  
 Интерфейс делегат, представляющий обработчик событий.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор EventSource::EventSource](../windows/eventsource-eventsource-constructor.md)|Инициализирует новый экземпляр класса EventSource.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод EventSource::Add](../windows/eventsource-add-method.md)|Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта EventSource.|  
|[Метод EventSource::GetSize](../windows/eventsource-getsize-method.md)|Возвращает число обработчиков событий, связанных с текущим объектом EventSource|  
|[Метод EventSource::InvokeAll](../windows/eventsource-invokeall-method.md)|Вызывает каждый обработчик событий, связанный с текущим объектом EventSource, с помощью указанных аргументов и их типов.|  
|[Метод EventSource::Remove](../windows/eventsource-remove-method.md)|Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим объектом EventSource.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[Элемент данных EventSource::addRemoveLock_](../windows/eventsource-addremovelock-data-member.md)|Синхронизирует доступ к [targets_](../windows/eventsource-targets-data-member.md) массива, при добавлении, удаление или вызывать обработчики событий.|  
|[Элемент данных EventSource::targets_](../windows/eventsource-targets-data-member.md)|Массив из одного или нескольких обработчиков событий.|  
|[Элемент данных EventSource::targetsPointerLock_](../windows/eventsource-targetspointerlock-data-member.md)|Синхронизирует доступ к членам внутренней данных даже в том случае, когда добавляются обработчики событий для этого события EventSource, удален или вызван.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EventSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
[AgileEventSource-класс](agileeventsource-class.md)
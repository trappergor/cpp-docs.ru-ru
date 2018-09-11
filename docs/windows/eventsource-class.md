---
title: Класс EventSource | Документация Майкрософт
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
ms.openlocfilehash: 8805547c5803ae665178330063e6b77b1b3c662e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596215"
---
# <a name="eventsource-class"></a>EventSource - класс

Представляет событие, отличный от agile. **EventSource** функции-члены добавлять, удалять и вызывать обработчики событий. Для гибкого событий использовать [AgileEventSource](agileeventsource-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Параметры

*TDelegateInterface*  
Интерфейс делегат, представляющий обработчик событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор EventSource::EventSource](../windows/eventsource-eventsource-constructor.md)|Инициализирует новый экземпляр класса **EventSource** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод EventSource::Add](../windows/eventsource-add-method.md)|Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего **EventSource** объекта.|
|[Метод EventSource::GetSize](../windows/eventsource-getsize-method.md)|Возвращает число обработчиков событий, связанных с текущим **EventSource** объекта|
|[Метод EventSource::InvokeAll](../windows/eventsource-invokeall-method.md)|Вызывает каждый обработчик событий, связанных с текущим **EventSource** объекта, используя указанным типам аргументов и аргументы.|
|[Метод EventSource::Remove](../windows/eventsource-remove-method.md)|Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим **EventSource** объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[Элемент данных EventSource::addRemoveLock_](../windows/eventsource-addremovelock-data-member.md)|Синхронизирует доступ к [targets_](../windows/eventsource-targets-data-member.md) массива, при добавлении, удалении или вызов обработчиков событий.|
|[Элемент данных EventSource::targets_](../windows/eventsource-targets-data-member.md)|Массив из одного или нескольких обработчиков событий.|
|[Элемент данных EventSource::targetsPointerLock_](../windows/eventsource-targetspointerlock-data-member.md)|Синхронизирует доступ к членам внутренних данных даже в том случае, когда добавляются обработчики событий для этого EventSource, удалены или вызове.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)  
[Класс AgileEventSource](agileeventsource-class.md)
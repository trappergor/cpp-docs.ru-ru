---
title: Класс EventSource | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 08347b4ccfa44d8645acc2bd5e96775bab4e7740
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601500"
---
# <a name="eventsource-class"></a>EventSource - класс

Представляет событие, отличный от agile. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий. Для гибкого событий использовать [AgileEventSource](agileeventsource-class.md).

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

| Имя                                     | Описание                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource::EventSource](#eventsource) | Инициализирует новый экземпляр класса `EventSource`. |

### <a name="public-methods"></a>Открытые методы

| Имя                                 | Описание                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::Add](#add)             | Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего `EventSource` объекта.                     |
| [EventSource::GetSize](#getsize)     | Возвращает число обработчиков событий, связанных с текущим `EventSource` объекта.                                                                         |
| [EventSource::InvokeAll](#invokeall) | Вызывает каждый обработчик событий, связанных с текущим `EventSource` объекта, используя указанным типам аргументов и аргументы.                                      |
| [EventSource::Remove](#remove)       | Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим `EventSource` объекта. |

### <a name="protected-data-members"></a>Защищенные члены данных

| name                                                    | Описание                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::addRemoveLock_](#addremovelock)           | Синхронизирует доступ к [targets_](#targets) массива, при добавлении, удалении или вызов обработчиков событий.                          |
| [EventSource::targets_](#targets)                       | Массив из одного или нескольких обработчиков событий.                                                                                           |
| [EventSource::targetsPointerLock_](#targetspointerlock) | Синхронизирует доступ к членам внутренних данных даже в том случае, когда добавляются обработчики событий для этого EventSource, удалены или вызове. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="add"></a>EventSource::Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего `EventSource` объекта.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Параметры

*delegateInterface*  
Интерфейс для объекта делегата, который представляет обработчик событий.

*Маркер*  
После завершения операции представляет дескриптор события. Используйте этот маркер в качестве параметра для [Remove()](#remove) метод для удаления обработчика событий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="addremovelock"></a>EventSource::addRemoveLock_

Синхронизирует доступ к [targets_](#targets) массива, при добавлении, удалении или вызов обработчиков событий.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>EventSource::EventSource

Инициализирует новый экземпляр класса `EventSource`.

```cpp
EventSource();
```

## <a name="getsize"></a>EventSource::GetSize

Возвращает число обработчиков событий, связанных с текущим `EventSource` объекта.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество обработчиков событий в [targets_](#targets).

## <a name="invokeall"></a>EventSource::InvokeAll

Вызывает каждый обработчик событий, связанных с текущим `EventSource` объекта, используя указанным типам аргументов и аргументы.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Параметры

*T0*  
Тип нулевого аргумента обработчика событий.

*T1*  
Тип первого аргумента обработчика событий.

*T2*  
Тип второго аргумента обработчика событий.

*T3*  
Тип третьего аргумента обработчика событий.

*T4*  
Тип четвертого аргумента обработчика событий.

*T5*  
Тип пятого аргумента обработчика событий.

*T6*  
Тип шестого аргумента обработчика событий.

*T7*  
Тип седьмого аргумента обработчика событий.

*T8*  
Тип восьмого аргумента обработчика событий.

*T9*  
Тип девятого аргумента обработчика событий.

*заполнитель с номером 0*  
Нулевой аргумент обработчика событий.

*arg1*  
Первый аргумент обработчика событий.

*Arg2*  
Второй аргумент обработчика событий.

*arg3*  
Третий аргумент обработчика событий.

*arg4*  
Четвертый аргумент обработчика событий.

*arg5*  
Пятый аргумент обработчика событий.

*arg6*  
Шестой аргумент обработчика событий.

*arg7*  
Седьмой аргумент обработчика событий.

*arg8*  
Восьмой аргумент обработчика событий.

*arg9*  
Девятый аргумент обработчика событий.

## <a name="remove"></a>EventSource::Remove

Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим `EventSource` объекта.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Параметры

*Маркер*  
Дескриптор, который представляет обработчик событий. Этот токен был возвращен при регистрации обработчика событий с [Add()](#add) метод.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Дополнительные сведения о `EventRegistrationToken` структуры, см. в разделе **структуры Windows::Foundation:: eventregistrationtoken** подразделы **среды выполнения Windows** справочной документации.

## <a name="targets"></a>EventSource::targets_

Массив из одного или нескольких обработчиков событий.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Примечания

Когда события, представленного текущим `EventSource` объект встречается, обработчики событий вызываются.

## <a name="targetspointerlock"></a>EventSource::targetsPointerLock_

Синхронизирует доступ к членам внутренние данные, даже когда обработчики событий для данного `EventSource` был добавлен, удален или вызванный.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```

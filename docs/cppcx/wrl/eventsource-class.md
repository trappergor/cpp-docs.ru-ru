---
title: Класс EventSource
ms.date: 09/12/2018
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
ms.openlocfilehash: 1350e51ff609a888b6a8ad6841be6856b68c7994
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821835"
---
# <a name="eventsource-class"></a>Класс EventSource

Представляет событие, не являющееся гибким. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий. Для гибких событий используйте [агиливентсаурце](agileeventsource-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Параметры

*тделегатеинтерфаце*<br/>
Интерфейс к делегату, который представляет обработчик событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

| Name                                     | Описание                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource:: EventSource](#eventsource) | Инициализация нового экземпляра класса `EventSource`. |

### <a name="public-methods"></a>Общедоступные методы

| Name                                 | Описание                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: Add](#add)             | Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта `EventSource`.                     |
| [EventSource:: DataSize](#getsize)     | Возвращает число обработчиков событий, связанных с текущим объектом `EventSource`.                                                                         |
| [EventSource:: InvokeAll](#invokeall) | Вызывает каждый обработчик событий, связанный с текущим объектом `EventSource`, используя указанные типы аргументов и аргументы.                                      |
| [EventSource:: Remove](#remove)       | Удаляет обработчик событий, представленный указанным токеном регистрации событий, из набора обработчиков событий, связанного с текущим объектом `EventSource`. |

### <a name="protected-data-members"></a>Защищенные элементы данных

| Name                                                    | Описание                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: addRemoveLock_](#addremovelock)           | Синхронизирует доступ к [targets_](#targets) массиву при добавлении, удалении или вызове обработчиков событий.                          |
| [EventSource:: targets_](#targets)                       | Массив из одного или нескольких обработчиков событий.                                                                                           |
| [EventSource:: targetsPointerLock_](#targetspointerlock) | Синхронизирует доступ к внутренним элементам данных, даже пока обработчики событий для этой EventSource добавляются, удаляются или вызываются. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

## <a name="requirements"></a>Требования

**Заголовок:** Event. h

**Пространство имен:** Microsoft::WRL

## <a name="add"></a>EventSource:: Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта `EventSource`.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Параметры

*delegateInterface*<br/>
Интерфейс для объекта делегата, который представляет обработчик событий.

*Лекс*<br/>
После завершения операции представляет дескриптор события. Используйте этот токен в качестве параметра метода [Remove ()](#remove) для отмены обработчика событий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="addremovelock"></a>EventSource:: addRemoveLock_

Синхронизирует доступ к [targets_](#targets) массиву при добавлении, удалении или вызове обработчиков событий.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>EventSource:: EventSource

Инициализация нового экземпляра класса `EventSource`.

```cpp
EventSource();
```

## <a name="getsize"></a>EventSource:: DataSize

Возвращает число обработчиков событий, связанных с текущим объектом `EventSource`.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число обработчиков событий в [targets_](#targets).

## <a name="invokeall"></a>EventSource:: InvokeAll

Вызывает каждый обработчик событий, связанный с текущим объектом `EventSource`, используя указанные типы аргументов и аргументы.

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

*T0*<br/>
Тип нулевого аргумента обработчика событий.

*T1*<br/>
Тип первого аргумента обработчика событий.

*T2*<br/>
Тип второго аргумента обработчика событий.

*T3*<br/>
Тип третьего аргумента обработчика событий.

*T4*<br/>
Тип четвертого аргумента обработчика событий.

*T5*<br/>
Тип пятого аргумента обработчика событий.

*T6*<br/>
Тип шестого аргумента обработчика событий.

*T7*<br/>
Тип седьмого аргумента обработчика событий.

*T8*<br/>
Тип аргумента восьмого обработчика событий.

*T9*<br/>
Тип девятого аргумента обработчика событий.

*arg0*<br/>
Нулевой аргумент обработчика событий.

*arg1*<br/>
Первый аргумент обработчика событий.

*arg2*<br/>
Второй аргумент обработчика событий.

*arg3*<br/>
Третий аргумент обработчика событий.

*arg4*<br/>
Четвертый аргумент обработчика событий.

*arg5*<br/>
Пятый аргумент обработчика событий.

*arg6*<br/>
Шестой аргумент обработчика событий.

*arg7*<br/>
Седьмой аргумент обработчика событий.

*arg8*<br/>
Восьмой аргумент обработчика событий.

*arg9*<br/>
Девятый аргумент обработчика событий.

## <a name="remove"></a>EventSource:: Remove

Удаляет обработчик событий, представленный указанным токеном регистрации событий, из набора обработчиков событий, связанного с текущим объектом `EventSource`.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Параметры

*Лекс*<br/>
Дескриптор, представляющий обработчик событий. Этот токен был возвращен, когда обработчик событий был зарегистрирован методом [Add ()](#add) .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Заметки

Дополнительные сведения о структуре `EventRegistrationToken` см. в разделе **Windows:: Foundation:: EventRegistrationToken Structure** в справочной документации по **Среда выполнения Windows** .

## <a name="targets"></a>EventSource:: targets_

Массив из одного или нескольких обработчиков событий.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Заметки

При возникновении события, представленного текущим объектом `EventSource`, вызываются обработчики событий.

## <a name="targetspointerlock"></a>EventSource:: targetsPointerLock_

Синхронизирует доступ к внутренним элементам данных даже при добавлении, удалении или вызове обработчиков событий для этого `EventSource`.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```

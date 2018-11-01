---
title: Класс EventTargetArray
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: e4973a8bc3d7a3f5fb6a9dcb76f79d55a05456f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648032"
---
# <a name="eventtargetarray-class"></a>Класс EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Примечания

Представляет собой массив обработчики событий.

Обработчики событий, связанных с [EventSource](../windows/eventsource-class.md) объекта хранятся в защищенный `EventTargetArray` элемент данных.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                           | Описание
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray::EventTargetArray](#eventtargetarray)        | Инициализирует новый экземпляр класса `EventTargetArray`.
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | Деинициализирует текущий `EventTargetArray` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                  | Описание
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.
[EventTargetArray::Begin](#begin)     | Получает адрес первого элемента во внутреннем массиве обработчиков событий.
[EventTargetArray::End](#end)         | Возвращает адрес последнего элемента в массиве внутренних обработчиков событий.
[EventTargetArray::Length](#length)   | Получает текущее число элементов в массиве внутренних обработчиков событий.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventTargetArray`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="tilde-eventtargetarray"></a>EventTargetArray:: ~ EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Примечания

Деинициализирует текущий `EventTargetArray` класса.

## <a name="addtail"></a>EventTargetArray::AddTail

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Указатель на обработчик событий для добавления.

### <a name="remarks"></a>Примечания

Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.

`AddTail()` предназначен для использования в среде только `EventSource` класса.

## <a name="begin"></a>EventTargetArray::Begin

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес первого элемента во внутреннем массиве обработчиков событий.

### <a name="remarks"></a>Примечания

Получает адрес первого элемента во внутреннем массиве обработчиков событий.

## <a name="end"></a>EventTargetArray::End

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес последнего элемента в массиве внутренних обработчиков событий.

### <a name="remarks"></a>Примечания

Возвращает адрес последнего элемента в массиве внутренних обработчиков событий.

## <a name="eventtargetarray"></a>EventTargetArray::EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Параметры

*hr*<br/>
После этого конструктор операций параметр *hr* указывает, успешно ли выполнено выделения массива. Ниже перечислены возможные значения для *hr*.

+   S_OK<br/>
    Операция успешно выполнена.

+   E_OUTOFMEMORY<br/>
    Не удалось выделить память для массива.

+   S_FALSE<br/>
    Параметр *элементы* меньше или равно нулю.

*Элементы*<br/>
Число элементов массива для выделения.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `EventTargetArray`.

`EventTargetArray` используется для сохранения массив дескрипторов событий в `EventSource` объекта.

## <a name="length"></a>EventTargetArray::Length

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
size_t Length();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество элементов в массиве внутренних обработчиков событий.

### <a name="remarks"></a>Примечания

Получает текущее число элементов в массиве внутренних обработчиков событий.

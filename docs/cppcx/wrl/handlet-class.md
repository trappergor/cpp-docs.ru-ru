---
title: HandleT - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: f66fbe23c305be15e09928242175dfa7ce8c141b
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821822"
---
# <a name="handlet-class"></a>HandleT - класс

Представляет дескриптор объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Параметры

*Метод HandleTraits*<br/>
Экземпляр структуры [метод HandleTraits](handletraits-structure.md) , определяющей общие характеристики маркера.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Открытые определения типов

Name     | Описание
-------- | -----------------------------
`Traits` | Синоним для `HandleTraits`.

### <a name="public-constructors"></a>Открытые конструкторы

Name                                | Описание
----------------------------------- | --------------------------------------------------
[Handleing:: Handle](#handlet)        | Инициализация нового экземпляра класса `HandleT`.
[Handleing:: ~ Handle](#tilde-handlet) | Выполняет деинициализацию экземпляра класса `HandleT`.

### <a name="public-methods"></a>Общедоступные методы

Name                         | Описание
---------------------------- | ----------------------------------------------------------------------
[Handle:: Attach](#attach)   | Связывает указанный маркер с текущим объектом `HandleT`.
[Handle:: Close](#close)     | Закрывает текущий объект `HandleT`.
[Handle::D етач](#detach)   | Отменяет связь текущего объекта `HandleT` с его базовым маркером.
[Handle:: Get](#get)         | Возвращает значение базового маркера.
[Handle:: IsValid](#isvalid) | Указывает, представляет ли текущий объект `HandleT` маркер.

### <a name="protected-methods"></a>Защищенные методы

Name                                     | Описание
---------------------------------------- | ------------------------------------
[Handle:: InternalClose](#internalclose) | Закрывает текущий объект `HandleT`.

### <a name="public-operators"></a>Открытые операторы

Name                                   | Описание
-------------------------------------- | ----------------------------------------------------------------------------------
[Handle:: operator =](#operator-assign) | Перемещает значение указанного объекта `HandleT` в текущий объект `HandleT`.

### <a name="protected-data-members"></a>Защищенные элементы данных

Name                        | Описание
--------------------------- | ----------------------------------------------------------------
[Handle:: handle_](#handle) | Содержит маркер, представленный объектом `HandleT`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс. h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="tilde-handlet"></a>Handleing:: ~ Handle

Выполняет деинициализацию экземпляра класса `HandleT`.

```cpp
~HandleT();
```

## <a name="attach"></a>Handle:: Attach

Связывает указанный маркер с текущим объектом `HandleT`.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Маркер.

## <a name="close"></a>Handle:: Close

Закрывает текущий объект `HandleT`.

```cpp
void Close();
```

### <a name="remarks"></a>Заметки

Маркер, лежащий в текущей `HandleT`, закрывается, а `HandleT` задается в недопустимом состоянии.

Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.

## <a name="detach"></a>Handle::D етач

Отменяет связь текущего объекта `HandleT` с его базовым маркером.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Базовый маркер.

### <a name="remarks"></a>Заметки

По завершении этой операции текущей `HandleT` присваивается недопустимое состояние.

## <a name="get"></a>Handle:: Get

Возвращает значение базового маркера.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер.

## <a name="handle"></a>Handle:: handle_

Содержит маркер, представленный объектом `HandleT`.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>Handleing:: Handle

Инициализация нового экземпляра класса `HandleT`.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Маркер.

### <a name="remarks"></a>Заметки

Первый конструктор инициализирует объект `HandleT`, который не является допустимым маркером для объекта. Второй конструктор создает новый объект `HandleT` из параметра *h*.

## <a name="internalclose"></a>Handle:: InternalClose

Закрывает текущий объект `HandleT`.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если текущий `HandleT` успешно закрыт; в противном случае — **значение false**.

### <a name="remarks"></a>Заметки

Параметр `InternalClose()` имеет значение `protected`.

## <a name="isvalid"></a>Handle:: IsValid

Указывает, представляет ли текущий объект `HandleT` маркер.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если `HandleT` представляет маркер; в противном случае — **значение false**.

## <a name="operator-assign"></a>Handle:: operator =

Перемещает значение указанного объекта `HandleT` в текущий объект `HandleT`.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на Handle.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект `HandleT`.

### <a name="remarks"></a>Заметки

Эта операция делает недействительным объект `HandleT`, указанный параметром *h*.

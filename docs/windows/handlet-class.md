---
title: Handlet-класс | Документация Майкрософт
ms.custom: ''
ms.date: 09/25/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb39d7418ece213e9c36c048fb5bcd3c000beca4
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235325"
---
# <a name="handlet-class"></a>HandleT - класс

Представляет дескриптор объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename HandleTraits
>
class HandleT;
```

### <a name="parameters"></a>Параметры

*HandleTraits*<br/>
Экземпляр [HandleTraits](../windows/handletraits-structure.md) структура, которая определяет общие характеристики дескриптора.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя     | Описание
-------- | -----------------------------
`Traits` | Синоним для `HandleTraits`.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | --------------------------------------------------
[HandleT::HandleT](#handlet)        | Инициализирует новый экземпляр класса `HandleT`.
[HandleT:: ~ HandleT](#tilde-handlet) | Отменяет инициализацию экземпляра `HandleT` класса.

### <a name="public-methods"></a>Открытые методы

Имя                         | Описание
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | Связывает указанный дескриптор с текущим `HandleT` объекта.
[HandleT::Close](#close)     | Закрывает текущий `HandleT` объекта.
[HandleT::Detach](#detach)   | Отсоединяет текущий `HandleT` объект из его базовый дескриптор.
[HandleT::Get](#get)         | Возвращает значение базового дескриптора.
[HandleT::IsValid](#isvalid) | Указывает, является ли текущий `HandleT` представляет дескриптор.

### <a name="protected-methods"></a>Защищенные методы

Имя                                     | Описание
---------------------------------------- | ------------------------------------
[HandleT::InternalClose](#internalclose) | Закрывает текущий `HandleT` объекта.

### <a name="public-operators"></a>Открытые операторы

Имя                                   | Описание
-------------------------------------- | ----------------------------------------------------------------------------------
[HandleT::operator =](#operator-assign) | Перемещает значение указанного `HandleT` объект с текущим `HandleT` объекта.

### <a name="protected-data-members"></a>Защищенные члены данных

name                        | Описание
--------------------------- | ----------------------------------------------------------------
[HandleT::handle_](#handle) | Содержит дескриптор, представленного `HandleT` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="tilde-handlet"></a>HandleT:: ~ HandleT

Отменяет инициализацию экземпляра `HandleT` класса.

```cpp
~HandleT();
```

## <a name="attach"></a>HandleT::Attach

Связывает указанный дескриптор с текущим `HandleT` объекта.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор.

## <a name="close"></a>HandleT::Close

Закрывает текущий `HandleT` объекта.

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

Дескриптор, лежащий в основе текущего `HandleT` закрывается и `HandleT` присваивается недопустимое состояние.

Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.

## <a name="detach"></a>HandleT::Detach

Отсоединяет текущий `HandleT` объект из его базовый дескриптор.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Базовый дескриптор.

### <a name="remarks"></a>Примечания

После завершения операции текущего `HandleT` присваивается недопустимое состояние.

## <a name="get"></a>HandleT::Get

Возвращает значение базового дескриптора.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор.

## <a name="handle"></a>HandleT::handle_

Содержит дескриптор, представленного `HandleT` объекта.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>HandleT::HandleT

Инициализирует новый экземпляр класса `HandleT`.

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
Дескриптор.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует `HandleT` объект, который не является допустимым дескриптором для объекта. Второй конструктор создает новый `HandleT` объект из параметра *h*.

## <a name="internalclose"></a>HandleT::InternalClose

Закрывает текущий `HandleT` объекта.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если текущий `HandleT` Закрыто успешно; в противном случае — значение `false`.

### <a name="remarks"></a>Примечания

Свойство `InternalClose()` имеет значение `protected`.

## <a name="isvalid"></a>HandleT::IsValid

Указывает, является ли текущий `HandleT` представляет дескриптор.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если `HandleT` представляет дескриптор; в противном случае `false`.

## <a name="operator-assign"></a>HandleT::operator =

Перемещает значение указанного `HandleT` объект с текущим `HandleT` объекта.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на дескриптор.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий `HandleT` объекта.

### <a name="remarks"></a>Примечания

Эта операция делает недействительным `HandleT` объекта, указанного параметром *h*.

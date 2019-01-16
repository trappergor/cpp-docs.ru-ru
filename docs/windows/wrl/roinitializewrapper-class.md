---
title: Класс RoInitializeWrapper
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: b43d5bb2f553d298584ab2ae497c22637d3beb0d
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336536"
---
# <a name="roinitializewrapper-class"></a>Класс RoInitializeWrapper

Инициализирует среду выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Примечания

`RoInitializeWrapper` — Это удобный инструмент, который инициализирует среду выполнения Windows и возвращает значение HRESULT, указывающее, является ли операция выполнена успешно. Так как вызывает деструктор класса `::Windows::Foundation::Uninitialize`, экземпляры `RoInitializeWrapper` должен быть объявлен в области глобального или верхнего уровня.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                    | Описание:
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper::RoInitializeWrapper](#roinitializewrapper)        | Инициализирует новый экземпляр класса `RoInitializeWrapper`.
[RoInitializeWrapper:: ~ RoInitializeWrapper](#tilde-roinitializewrapper) | Удаляет текущий экземпляр `RoInitializeWrapper` класса.

### <a name="public-operators"></a>Открытые операторы

Имя                                       | Описание
------------------------------------------ | ------------------------------------------------------------------------
[Roinitializewrapper:: HRESULT()](#hresult) | Возвращает значение HRESULT `RoInitializeWrapper` конструктор.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RoInitializeWrapper`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="hresult"></a>Roinitializewrapper:: HRESULT()

Получает значение HRESULT, создаваемое при последнем `RoInitializeWrapper` конструктор.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapper"></a>RoInitializeWrapper::RoInitializeWrapper

Инициализирует новый экземпляр класса `RoInitializeWrapper`.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Одно из перечислений RO_INIT_TYPE, которые задает поддержку, предоставляемые средой выполнения Windows.

### <a name="remarks"></a>Примечания

`RoInitializeWrapper` Класс вызывает `Windows::Foundation::Initialize(flags)`.

## <a name="tilde-roinitializewrapper"></a>RoInitializeWrapper:: ~ RoInitializeWrapper

Отменяет инициализацию среды выполнения Windows.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Примечания

`RoInitializeWrapper` Класс вызывает `Windows::Foundation::Uninitialize()`.

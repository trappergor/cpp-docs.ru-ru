---
title: Класс RoInitializeWrapper | Документация Майкрософт
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22271435db3a66095da5b6065a6b9cc9463b3de2
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233753"
---
# <a name="roinitializewrapper-class"></a>Класс RoInitializeWrapper

Инициализирует среду выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class RoInitializeWrapper
```

## <a name="remarks"></a>Примечания

`RoInitializeWrapper` — Это удобный инструмент, который инициализирует среду выполнения Windows и возвращает значение HRESULT, указывающее, является ли операция выполнена успешно. Так как вызывает деструктор класса `::Windows::Foundation::Uninitialize`, экземпляры `RoInitializeWrapper` должен быть объявлен в области глобального или верхнего уровня.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                    | Описание
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

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="hresult"></a>Roinitializewrapper:: HRESULT()

Получает значение HRESULT, создаваемое при последнем `RoInitializeWrapper` конструктор.

```cpp
operator HRESULT()  
```

## <a name="roinitializewrapper"></a>RoInitializeWrapper::RoInitializeWrapper

Инициализирует новый экземпляр класса `RoInitializeWrapper`.

```cpp
RoInitializeWrapper(   RO_INIT_TYPE flags)  
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

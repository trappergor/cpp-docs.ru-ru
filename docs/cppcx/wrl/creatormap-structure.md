---
title: CreatorMap - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 44d06f317661059bea92d8c6f27955606a964bb7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785220"
---
# <a name="creatormap-structure"></a>CreatorMap - структура

Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Примечания

Содержит сведения о том, как инициализировать, регистрации и отмены регистрации объектов.

`CreatorMap` содержит следующие сведения:

- Как инициализировать, регистрации и отмены регистрации объектов.

- Как сравнить данные активации, в зависимости от традиционную фабрику COM или среду выполнения Windows.

- Сведения об имени фабрики кэша и сервера для интерфейса.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

name                                          | Описание
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap::activationId](#activationid)     | Представляет идентификатор объекта, который определяется либо идентификатор классического COM-класса, либо указать имя среды выполнения Windows.
[CreatorMap::factoryCache](#factorycache)     | Сохраняет указатель на кэш фабрики для `CreatorMap`.
[CreatorMap::factoryCreator](#factorycreator) | Создает фабрику для указанного `CreatorMap`.
[CreatorMap::serverName](#servername)         | Хранит имя сервера для `CreatorMap`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CreatorMap`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="activationid"></a>CreatorMap::activationId

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Идентификатор интерфейса.

*getRuntimeName*<br/>
Функция, которая извлекает имя объекта в среде выполнения Windows.

### <a name="remarks"></a>Примечания

Представляет идентификатор объекта, который определен идентификатором класса классической модели COM или именем в среде выполнения Windows.

## <a name="factorycache"></a>CreatorMap::factoryCache

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Примечания

Сохраняет указатель на кэш фабрики для `CreatorMap`.

## <a name="factorycreator"></a>CreatorMap::factoryCreator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Параметры

*currentflags*<br/>
Один из [RuntimeClassType](runtimeclasstype-enumeration.md) перечислителей.

*entry*<br/>
CreatorMap.

*iidClassFactory*<br/>
Идентификатор интерфейса фабрики класса.

*фабрики*<br/>
После завершения операции адрес фабрики класса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Создает фабрику для указанного объекта CreatorMap.

## <a name="servername"></a>CreatorMap::serverName

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Примечания

Хранит имя сервера для объекта CreatorMap.

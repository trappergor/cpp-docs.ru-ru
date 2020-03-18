---
title: Класс Module::ReleaseNotifier
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: 5fc1b8965bf8bf2f86dd30f2195fa825f85f6d7e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423630"
---
# <a name="modulereleasenotifier-class"></a>Класс Module::ReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в модуле.

## <a name="syntax"></a>Синтаксис

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                | Description
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Модуль:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Выполняет деинициализацию текущего экземпляра класса `Module::ReleaseNotifier`.
[Модуль:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Description
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Модуль:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | При реализации вызывает обработчик событий при освобождении последнего объекта в модуле.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Удаляет текущий объект `Module::ReleaseNotifier`, если объект был создан с параметром, равным **true**.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** Module. h

**Пространство имен:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Модуль:: ReleaseNotifier:: ~ ReleaseNotifier

Выполняет деинициализацию текущего экземпляра класса `Module::ReleaseNotifier`.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Модуль:: ReleaseNotifier:: Invoke

При реализации вызывает обработчик событий при освобождении последнего объекта в модуле.

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Модуль:: ReleaseNotifier:: Release

Удаляет текущий объект `Module::ReleaseNotifier`, если объект был создан с параметром, равным **true**.

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Модуль:: ReleaseNotifier:: ReleaseNotifier

Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Параметры

*release*<br/>
`true` удалить этот экземпляр при вызове метода `Release`; `false`, чтобы не удалять этот экземпляр.

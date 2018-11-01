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
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475911"
---
# <a name="modulereleasenotifier-class"></a>Класс Module::ReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в модуле.

## <a name="syntax"></a>Синтаксис

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                | Описание
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module::ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Деинициализирует текущий экземпляр `Module::ReleaseNotifier` класса.
[Module::releasenotifier:: releasenotifier](#releasenotifier-releasenotifier)        | Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module::ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | При реализации, вызывает обработчик событий при освобождении последнего объекта в модуле.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Удаляет текущий `Module::ReleaseNotifier` объекта, если объект был создан с параметром **true**.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module::ReleaseNotifier:: ~ ReleaseNotifier

Деинициализирует текущий экземпляр `Module::ReleaseNotifier` класса.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module::ReleaseNotifier:: Invoke

При реализации, вызывает обработчик событий при освобождении последнего объекта в модуле.

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module::ReleaseNotifier::Release

Удаляет текущий `Module::ReleaseNotifier` объекта, если объект был создан с параметром **true**.

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module::releasenotifier:: releasenotifier

Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Параметры

*release*<br/>
`true` Чтобы удалить это экземпляром при `Release` вызове метода; `false` не удалить этот экземпляр.

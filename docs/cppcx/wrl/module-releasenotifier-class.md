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
ms.openlocfilehash: f314d09c443d0d284e3a821b5c879bfb74baf812
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371279"
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
[Модуль::ReleaseNotifier:: »ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Деприиратизирует текущий `Module::ReleaseNotifier` экземпляр класса.
[Модуль::ReleaseNotifier:ReleaseNotifier](#releasenotifier-releasenotifier)        | Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Модуль:ReleaseNotifier::Invoke](#releasenotifier-invoke)   | При реализации вызовит обработчик событий при освобождении последнего объекта в модуле.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Удаляет текущий `Module::ReleaseNotifier` объект, если объект был построен с параметром **истинного.**

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>Модуль::ReleaseNotifier:: »ReleaseNotifier

Деприиратизирует текущий `Module::ReleaseNotifier` экземпляр класса.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>Модуль:ReleaseNotifier::Invoke

При реализации вызовит обработчик событий при освобождении последнего объекта в модуле.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>Модуль::ReleaseNotifier::Release

Удаляет текущий `Module::ReleaseNotifier` объект, если объект был построен с параметром **истинного.**

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>Модуль::ReleaseNotifier:ReleaseNotifier

Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Параметры

*Выпуска*<br/>
`true`удалить этот экземпляр `Release` при вызове метода; `false` не удалять этот экземпляр.

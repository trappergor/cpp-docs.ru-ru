---
title: Класс Module::MethodReleaseNotifier
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: c2b37073455f255eaea931e7aaedd1e34a14a104
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469346"
---
# <a name="modulemethodreleasenotifier-class"></a>Класс Module::MethodReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий заданного объекта и ее члена указатель на метод.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, функция-член которого является обработчиком событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                                 | Описание
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module::methodreleasenotifier:: methodreleasenotifier](#methodreleasenotifier-methodreleasenotifier) | Инициализирует новый экземпляр класса `Module::MethodReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                                   | Описание
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier:: Invoke](#methodreleasenotifier-invoke) | Вызывает обработчик событий, связанный с текущим `Module::MethodReleaseNotifier` объекта.

### <a name="protected-data-members"></a>Защищенные члены данных

name                                                                    | Описание
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module::MethodReleaseNotifier::method_](#methodreleasenotifier-method) | Содержит указатель на обработчик событий для текущего `Module::MethodReleaseNotifier` объекта.
[Module::MethodReleaseNotifier::object_](#methodreleasenotifier-object) | Содержит указатель на объект, функция-член которого является обработчиком событий для текущего `Module::MethodReleaseNotifier` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="methodreleasenotifier-invoke"></a>Module::MethodReleaseNotifier:: Invoke

Вызывает обработчик событий, связанный с текущим `Module::MethodReleaseNotifier` объекта.

```cpp
void Invoke();
```

## <a name="methodreleasenotifier-method"></a>Module::MethodReleaseNotifier::method_

Содержит указатель на обработчик событий для текущего `Module::MethodReleaseNotifier` объекта.

```cpp
void (T::* method_)();
```

## <a name="methodreleasenotifier-methodreleasenotifier"></a>Module::methodreleasenotifier:: methodreleasenotifier

Инициализирует новый экземпляр класса `Module::MethodReleaseNotifier`.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>Параметры

*object*<br/>
Объект, функция-член которого является обработчиком событий.

*Метод*<br/>
Функция-член параметра *объект* то есть обработчик событий.

*release*<br/>
Укажите **true** для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-class.md#releasenotifier-release) метода; в противном случае укажите **false**.

## <a name="methodreleasenotifier-object"></a>Module::MethodReleaseNotifier::object_

Содержит указатель на объект, функция-член которого является обработчиком событий для текущего `Module::MethodReleaseNotifier` объекта.

```cpp
T* object_;
```

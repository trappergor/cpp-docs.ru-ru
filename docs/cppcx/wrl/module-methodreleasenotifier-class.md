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
ms.openlocfilehash: c641f150b6f029facffa62f7b47c7da32138735e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371291"
---
# <a name="modulemethodreleasenotifier-class"></a>Класс Module::MethodReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик события определяется объектом и его элементом указателя на метод.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, функцией члена которого является обработчик события.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                                 | Описание
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Модуль:MethodReleaseNotifier::MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | Инициализирует новый экземпляр класса `Module::MethodReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                                   | Описание
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Модуль:MethodReleaseNotifier::Invoke](#methodreleasenotifier-invoke) | Вызывает обработчик событий, `Module::MethodReleaseNotifier` связанный с текущим объектом.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                                                    | Описание
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Модуль:MethodReleaseNotifier::method_](#methodreleasenotifier-method) | Удерживает указатель обработчика событий `Module::MethodReleaseNotifier` для текущего объекта.
[Модуль:MethodReleaseNotifier::object_](#methodreleasenotifier-object) | Удерживает указатель на объект, функция члена которого `Module::MethodReleaseNotifier` является обработчиком событий для текущего объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>Модуль:MethodReleaseNotifier::Invoke

Вызывает обработчик событий, `Module::MethodReleaseNotifier` связанный с текущим объектом.

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>Модуль:MethodReleaseNotifier::method_

Удерживает указатель обработчика событий `Module::MethodReleaseNotifier` для текущего объекта.

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>Модуль:MethodReleaseNotifier::MethodReleaseNotifier

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

*Объекта*<br/>
Объект, функция члена которого является обработчиком событий.

*method*<br/>
Функция участника *объекта* параметра, который является обработчиком событий.

*Выпуска*<br/>
Указать, `true` чтобы включить вызов основного [модуля::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) метод; в противном случае, укажите `false`.

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>Модуль:MethodReleaseNotifier::object_

Удерживает указатель на объект, функция члена которого `Module::MethodReleaseNotifier` является обработчиком событий для текущего объекта.

```cpp
T* object_;
```

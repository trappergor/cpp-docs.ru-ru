---
title: Класс Module::GenericReleaseNotifier
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: c708dc101fde9d2631eca33ebe101f4aed421094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572358"
---
# <a name="modulegenericreleasenotifier-class"></a>Класс Module::GenericReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных-члена, который содержит расположение обработчика событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                                     | Описание
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module::genericreleasenotifier:: genericreleasenotifier](#genericreleasenotifier-genericreleasenotifier) | Инициализирует новый экземпляр класса `Module::GenericReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                                     | Описание
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier:: Invoke](#genericreleasenotifier-invoke) | Вызывает обработчик событий, связанный с текущим `Module::GenericReleaseNotifier` объекта.

### <a name="protected-data-members"></a>Защищенные члены данных

name                                                                          | Описание
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier::callback_](#genericreleasenotifier-callback) | Содержит лямбда-выражения, функтором или обработчик событий указателя на функцию, связанный с текущим `Module::GenericReleaseNotifier` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="genericreleasenotifier-callback"></a>Module::GenericReleaseNotifier::callback_

Содержит лямбда-выражения, функтором или обработчик событий указателя на функцию, связанный с текущим `Module::GenericReleaseNotifier` объекта.

```cpp
T callback_;
```

## <a name="genericreleasenotifier-genericreleasenotifier"></a>Module::genericreleasenotifier:: genericreleasenotifier

Инициализирует новый экземпляр класса `Module::GenericReleaseNotifier`.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Параметры

*обратный вызов*<br/>
Лямбда-выражения, функтором или обработчик событий указателя на функцию, который может быть вызван с помощью функции оператор «скобки» (`()`).

*release*<br/>
Укажите **true** для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите **false**.

## <a name="genericreleasenotifier-invoke"></a>Module::GenericReleaseNotifier:: Invoke

Вызывает обработчик событий, связанный с текущим `Module::GenericReleaseNotifier` объекта.

```cpp
void Invoke();
```

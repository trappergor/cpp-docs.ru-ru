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
ms.openlocfilehash: e3cc8e33d596fb1d3ecc4a94fee7971a50ffe596
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371309"
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
[Модуль::GenericReleaseNotifier::GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | Инициализирует новый экземпляр класса `Module::GenericReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

Имя                                                                     | Описание
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Модуль::GenericReleaseNotifier::Invoke](#genericreleasenotifier-invoke) | Вызывает обработчик событий, `Module::GenericReleaseNotifier` связанный с текущим объектом.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                                                          | Описание
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Модуль::GenericReleaseNotifier::callback_](#genericreleasenotifier-callback) | Удерживает лямбду, фанктор или обработчик событий, связанный `Module::GenericReleaseNotifier` с текущим объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>Модуль::GenericReleaseNotifier::callback_

Удерживает лямбду, фанктор или обработчик событий, связанный `Module::GenericReleaseNotifier` с текущим объектом.

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>Модуль::GenericReleaseNotifier::GenericReleaseNotifier

Инициализирует новый экземпляр класса `Module::GenericReleaseNotifier`.

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>Параметры

*обратный вызов*<br/>
Lambda, functor, или обработчик событий указателя к функции, который может быть`()`вызван с оператором функции скобки ( ).

*Выпуска*<br/>
Указать, `true` чтобы включить вызов основного [модуля::ReleaseNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release) метод; в противном случае, укажите `false`.

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>Модуль::GenericReleaseNotifier::Invoke

Вызывает обработчик событий, `Module::GenericReleaseNotifier` связанный с текущим объектом.

```cpp
void Invoke();
```

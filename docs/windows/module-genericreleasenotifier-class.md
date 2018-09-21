---
title: Класс Module::GenericReleaseNotifier | Документация Майкрософт
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18aeac7767fbd4c1688b202670a812e5738ef62f
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494430"
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

*обратный вызов*  
Лямбда-выражения, функтором или обработчик событий указателя на функцию, который может быть вызван с помощью функции оператор «скобки» (`()`).

*release*  
Укажите `true` для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите `false`.

## <a name="genericreleasenotifier-invoke"></a>Module::GenericReleaseNotifier:: Invoke

Вызывает обработчик событий, связанный с текущим `Module::GenericReleaseNotifier` объекта.

```cpp
void Invoke();
```

---
title: Класс Module::GenericReleaseNotifier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b04600f1f464220b00749903f27826855f6000
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400267"
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

|Имя|Описание|
|----------|-----------------|
|[Конструктор Module::GenericReleaseNotifier::GenericReleaseNotifier](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Инициализирует новый экземпляр класса **Module::GenericReleaseNotifier** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод Module::GenericReleaseNotifier::Invoke](../windows/module-genericreleasenotifier-invoke-method.md)|Вызывает обработчик событий, связанный с текущим **Module::GenericReleaseNotifier** объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Элемент данных Module::GenericReleaseNotifier::callback_](../windows/module-genericreleasenotifier-callback-data-member.md)|Содержит лямбда-выражения, функтором или обработчик событий указателя на функцию, связанный с текущим **Module::GenericReleaseNotifier** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)
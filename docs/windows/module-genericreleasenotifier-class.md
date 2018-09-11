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
ms.openlocfilehash: da35e2c257fef72ea75e05768960098111727359
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611629"
---
# <a name="modulegenericreleasenotifier-class"></a>Класс Module::GenericReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Параметры

*T*  
Тип данных-члена, который содержит расположение обработчика событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор Module::GenericReleaseNotifier::GenericReleaseNotifier](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Инициализирует новый экземпляр класса **Module::GenericReleaseNotifier** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод Module::GenericReleaseNotifier::Invoke](../windows/module-genericreleasenotifier-invoke-method.md)|Вызывает обработчик событий, связанный с текущим **Module::GenericReleaseNotifier** объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
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
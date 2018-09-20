---
title: Класс Module::ReleaseNotifier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b42d4c282ce710f2f08b41c4097d64aa4dc9a805
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407313"
---
# <a name="modulereleasenotifier-class"></a>Класс Module::ReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в модуле.

## <a name="syntax"></a>Синтаксис

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Деструктор Module::ReleaseNotifier::~ReleaseNotifier](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Деинициализирует текущий экземпляр **Module::ReleaseNotifier** класса.|
|[Конструктор Module::ReleaseNotifier::ReleaseNotifier](../windows/module-releasenotifier-releasenotifier-constructor.md)|Инициализирует новый экземпляр класса **Module::ReleaseNotifier** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод Module::ReleaseNotifier::Invoke](../windows/module-releasenotifier-invoke-method.md)|При реализации, вызывает обработчик событий при освобождении последнего объекта в модуле.|
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Удаляет текущий **Module::ReleaseNotifier** объекта, если объект был создан с параметром **true**.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module](../windows/module-class.md)
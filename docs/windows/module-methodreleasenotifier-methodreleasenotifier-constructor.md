---
title: 'Конструктор Module::methodreleasenotifier:: methodreleasenotifier | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 608a885eb446860cca43e5fabd19597d7611e633
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386826"
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier

Инициализирует новый экземпляр класса **Module::MethodReleaseNotifier** класса.

## <a name="syntax"></a>Синтаксис

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
Укажите **true** для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите **false**.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)
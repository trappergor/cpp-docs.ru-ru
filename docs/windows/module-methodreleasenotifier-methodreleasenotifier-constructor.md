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
ms.openlocfilehash: 62f136fb9aac184d6ca81314aafea270e7b33a87
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583875"
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

*object*  
Объект, функция-член которого является обработчиком событий.

*Метод*  
Функция-член параметра *объект* то есть обработчик событий.

*release*  
Укажите **true** для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите **false**.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)
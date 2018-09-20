---
title: 'Конструктор Module::releasenotifier:: releasenotifier | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e43abd46ccfb150936ff435360611289f18a1270
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405025"
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Конструктор Module::ReleaseNotifier::ReleaseNotifier

Инициализирует новый экземпляр класса **Module::ReleaseNotifier** класса.

## <a name="syntax"></a>Синтаксис

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Параметры

*release*<br/>
**значение true,** удалить данный экземпляр, когда `Release` вызове метода; **false** не удалить этот экземпляр.

## <a name="exceptions"></a>Исключения

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)
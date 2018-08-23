---
title: Пространство имен Microsoft::WRL::Wrappers::Details | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
dev_langs:
- C++
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3af5add0a934b59cf3027b7beb0ea000a7ae1415
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595711"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::Details

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|Имя|Описание:|
|----------|-----------------|
|[Класс SyncLockT](../windows/synclockt-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|
|[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|

### <a name="methods"></a>Методы

|Имя|Описание:|
|----------|-----------------|
|[Метод CompareStringOrdinal](../windows/comparestringordinal-method.md)|Сравнивает два указанных `HSTRING` объектов и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)
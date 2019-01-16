---
title: Пространство имен Microsoft::WRL::Wrappers::Details
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
ms.openlocfilehash: d02b19863ffa14e0edb3b1a96dceb936037743d3
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336834"
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
|[Класс SyncLockT](synclockt-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|
|[Класс SyncLockWithStatusT](synclockwithstatust-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|

### <a name="methods"></a>Методы

|Имя|Описание:|
|----------|-----------------|
|[Метод CompareStringOrdinal](comparestringordinal-method.md)|Сравнивает два указанных `HSTRING` объектов и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)
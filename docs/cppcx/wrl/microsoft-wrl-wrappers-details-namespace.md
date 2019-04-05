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
ms.openlocfilehash: deccd4519b2ddf18725dca5af13b94ac79d6e280
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038726"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::Details

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[SyncLockT - класс](synclockt-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|
|[Класс SyncLockWithStatusT](synclockwithstatust-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|

### <a name="methods"></a>Методы

|name|Описание|
|----------|-----------------|
|[Метод CompareStringOrdinal](comparestringordinal-method.md)|Сравнивает два указанных `HSTRING` объектов и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)
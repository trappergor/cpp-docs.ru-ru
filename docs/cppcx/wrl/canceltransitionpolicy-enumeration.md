---
title: CancelTransitionPolicy - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: cfd8e25f98ec1001a8fbd287eaec12408b9f240e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784745"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy - перечисление

Показывает, как попытка перехода асинхронной операции к окончательному состоянию завершения или ошибки должна происходить с учетом запрошенного клиентом состояния отмены.

## <a name="syntax"></a>Синтаксис

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Участники

### <a name="values"></a>Значения

|name|Описание|
|----------|-----------------|
|`RemainCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что данный элемент остается в отмененном состоянии, в отличие от перехода к окончательному состоянию завершения или ошибки.|
|`TransitionFromCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что состояние должно перейти из данного состояния отмены в окончательное состояние завершения или ошибки, как определено вызовом, который использует этот флажок.|

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
---
title: Метод ChainInterfaces::CanCastTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 752c3598a38117506154b0a2b7d7d3e578bf3c3e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417648"
---
# <a name="chaininterfacescancastto-method"></a>Метод ChainInterfaces::CanCastTo

Указывает ли идентификатор указанный интерфейс может быть приведен к каждому из специализаций, определяемая параметрами шаблона не по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppv*<br/>
Указатель на последний идентификатор интерфейса, который был приведен успешно.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если все операции приведения выполнена успешно; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)
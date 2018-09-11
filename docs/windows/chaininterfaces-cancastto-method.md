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
ms.openlocfilehash: 8398f0bd4d9fdc786926782b13ebcac913a6a351
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612874"
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

*riid*  
Идентификатор интерфейса.

*ppv*  
Указатель на последний идентификатор интерфейса, который был приведен успешно.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если все операции приведения выполнена успешно; в противном случае **false**.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)
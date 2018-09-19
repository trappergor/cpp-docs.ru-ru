---
title: Asyncstatusinternal-перечисление | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c7751929a55993876034bb3c1918b82193681fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016888"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal - перечисление

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Примечания

Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.

## <a name="members"></a>Участники

`_Created`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Created`.

`_Started`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Started`.

`_Completed`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Completed`.

`_Cancelled`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Cancelled`.

`_Error`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Error`.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)
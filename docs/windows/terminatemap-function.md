---
title: Функция TerminateMap
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: efee7edfc1085288b3220698024cb0deeb4e71af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643226"
---
# <a name="terminatemap-function"></a>Функция TerminateMap

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Параметры

*module*<br/>
Объект [модуль](../windows/module-class.md).

*Имя_сервера*<br/>
Имя подмножества фабрик классов в модуль, указанный параметром *модуль*.

*forceTerminate*<br/>
**значение true,** завершить класс фабрик, независимо от того, они активны; **false** чтобы не завершать работу фабрик классов, если какая-либо активен.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если всех фабрик классов была завершена; в противном случае — значение **false**.

## <a name="remarks"></a>Примечания

Завершает работу фабрик классов в указанном модуле.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)
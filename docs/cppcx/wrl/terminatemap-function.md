---
title: Функция TerminateMap
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 560f563e43fc8b818b04cd0bda6b01fbc916cb84
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213555"
---
# <a name="terminatemap-function"></a>Функция TerminateMap

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Параметры

*module*<br/>
[Модуль](module-class.md).

*serverName*<br/>
Имя подмножества фабрик класса в модуле, заданном *модулем*параметров.

*форцетерминате*<br/>
**значение true** , чтобы завершить фабрики класса независимо от того, активны они. **значение false** , чтобы не завершать фабрики класса, если активна какая-либо фабрика.

## <a name="return-value"></a>Возвращаемое значение

**значение true** , если все фабрики класса были завершены. в противном случае — **значение false**.

## <a name="remarks"></a>Remarks

Завершает работу фабрик классов в указанном модуле.

## <a name="requirements"></a>Требования

**Заголовок:** Module. h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)

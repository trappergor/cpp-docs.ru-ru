---
title: Глобальные функции контекста устройства
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: e640f310a1976c29a39f0ab7c2575dfd1073c889
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330156"
---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства

Эта функция создает контекст устройства для данного устройства.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>AtlCreateTargetDC

Создает контекст устройства для устройства, указанного в структуре [DVTARGET.](/windows/win32/api/objidl/ns-objidl-dvtargetdevice)

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Параметры

*Hdc*<br/>
(в) Существующая ручка контекста устройства, или NULL.

*ptd*<br/>
(в) Указатель на `DVTARGETDEVICE` структуру, содержащую информацию о целевом устройстве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в контекст устройства для `DVTARGETDEVICE`устройства, указанного в . Если устройство не указано, возвращает ручку устройству дисплея по умолчанию.

### <a name="remarks"></a>Remarks

Если структура NULL, а *HDC* null, создает контекст устройства для устройства дисплея по умолчанию.

Если *HDC* не является NULL и *ptd* является NULL, функция возвращает существующий *HDc*.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)

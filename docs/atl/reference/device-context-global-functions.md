---
title: Глобальные функции контекста устройства
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: 25ceae897d3cc845ab06fd4d898c87518b15eacb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551207"
---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства

Эта функция создает контекст устройства для данного устройства.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|

##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC

Создает контекст устройства для устройства, заданного в [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) структуры.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Параметры

*hdc*<br/>
[in] Существующий дескриптор контекста устройства, или значение NULL.

*ptd*<br/>
[in] Указатель на `DVTARGETDEVICE` структуру, содержащую сведения о целевом устройстве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор контекста устройства для устройства, заданного в `DVTARGETDEVICE`. Если устройство не указано, возвращает дескриптор для устройства отображения по умолчанию.

### <a name="remarks"></a>Примечания

Если структура имеет значение NULL и *hdc* имеет значение NULL, создает контекст устройства для устройства отображения по умолчанию.

Если *hdc* не равно NULL и *ptd* имеет значение NULL, функция возвращает существующий *hdc*.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)

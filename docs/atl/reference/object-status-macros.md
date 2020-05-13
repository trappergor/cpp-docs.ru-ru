---
title: Макрос состояния объекта
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 5617ce7fb972c98775072f72244f91052d41ece3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326168"
---
# <a name="object-status-macros"></a>Макрос состояния объекта

На этом макросе устанавливаются флаги, принадлежащие элементам управления ActiveX.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Используется в элементах управления ATL ActiveX для установки флагов OLEMISC.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

Используется в элементах управления ATL ActiveX для установки флагов OLEMISC.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Параметры

*неверный*<br/>
Все применимые флаги OLEMISC.

### <a name="remarks"></a>Remarks

Этот макрос используется для установки флагов OLEMISC для управления ActiveX. Для получения более подробной информации обратитесь к [IOleObject::GetMiscStatus.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)

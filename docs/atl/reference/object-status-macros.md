---
title: Макросы состояния объекта
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: dc50825d6b6e74dc263a097e86d8ea0d42989825
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495321"
---
# <a name="object-status-macros"></a>Макросы состояния объекта

Этот макрос задает флаги, принадлежащие элементам управления ActiveX.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Используется в элементах управления ActiveX ATL для установки флагов ОЛЕМИСК.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

Используется в элементах управления ActiveX ATL для установки флагов ОЛЕМИСК.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Параметры

*мискстатус*<br/>
Все применимые флаги ОЛЕМИСК.

### <a name="remarks"></a>Примечания

Этот макрос используется для установки флагов ОЛЕМИСК для элемента управления ActiveX. Дополнительные сведения см. в разделе [иолеобжект:: жетмискстатус](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)

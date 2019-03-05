---
title: Макросы состояния объектов
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: cb5ff6d7570b03b32852fc450f58043446f721f4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267273"
---
# <a name="object-status-macros"></a>Макросы состояния объектов

Этот макрос задает флаги, относящиеся к элементам управления ActiveX.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Используется в элементах управления ActiveX библиотеки ATL, чтобы задать флаги OLEMISC.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS

Используется в элементах управления ActiveX библиотеки ATL, чтобы задать флаги OLEMISC.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Параметры

*MiscStatus*<br/>
Все установленные флаги OLEMISC.

### <a name="remarks"></a>Примечания

Этот макрос используется, чтобы задать флаги OLEMISC для элемента управления ActiveX. Ссылаться на [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) для получения дополнительных сведений.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)

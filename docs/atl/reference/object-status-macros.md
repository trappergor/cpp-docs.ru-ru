---
title: Объект состояния макросы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04bad7c90869eb5a5b87a465b175e4ed3f0b9991
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751515"
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

*MiscStatus*  
Все установленные флаги OLEMISC.

### <a name="remarks"></a>Примечания

Этот макрос используется, чтобы задать флаги OLEMISC для элемента управления ActiveX. Ссылаться на [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) для получения дополнительных сведений.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)

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
ms.openlocfilehash: c4b8be9cf1b421a66081fcf650462447d3c0ef7e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052542"
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

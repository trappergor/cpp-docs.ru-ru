---
title: COM Карта Макрос
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 191a0ba0aeda6ad18cdac7ba14f7ab5f3b2282f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326603"
---
# <a name="com-map-macros"></a>COM Карта Макрос

Эти макросы определяют карты интерфейса COM.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|Отмечает начало записи карты интерфейса COM.|
|[END_COM_MAP](#end_com_map)|Отметки конца записей карты интерфейса COM.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_com_map"></a><a name="begin_com_map"></a>BEGIN_COM_MAP

Карта COM — это механизм, который предоставляет интерфейсы `QueryInterface`на объекте клиенту через.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название объекта класса, на который вы подвергаете интерфейсы.

### <a name="remarks"></a>Remarks

[CComObjectRootEx::Internal'ryInterface](ccomobjectrootex-class.md#internalqueryinterface) возвращает только указатели для интерфейсов на карте COM. Начните свою карту интерфейса с BEGIN_COM_MAP макроса, добавьте записи для каждого из интерфейсов с [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) макросом или одним из его вариантов, а также завершите карту [с END_COM_MAP](#end_com_map) макросом.

### <a name="example"></a>Пример

Из образца ATL [BEEPER:](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a>END_COM_MAP

Завершает определение вашей карты интерфейса COM.

```
END_COM_MAP()
```

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[COM Карта Глобальные функции](../../atl/reference/com-map-global-functions.md)

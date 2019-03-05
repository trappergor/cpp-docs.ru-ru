---
title: Макросы сопоставления COM
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: dbb84814c6865b5b666a8b3a1162e81a211de1eb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280710"
---
# <a name="com-map-macros"></a>Макросы сопоставления COM

Эти макросы определяют схемы интерфейсов COM.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|Отмечает начало карты записей интерфейс COM.|
|[END_COM_MAP](#end_com_map)|Помечает конец интерфейса COM карты записей.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="begin_com_map"></a>  BEGIN_COM_MAP

В сопоставление COM — механизм, который предоставляет интерфейсы объекта клиенту с помощью `QueryInterface`.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя объекта класса, которую необходимо предоставить интерфейсы на.

### <a name="remarks"></a>Примечания

[CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) возвращает только указатели для интерфейсов COM карты. Запустите схему интерфейсов макрос BEGIN_COM_MAP, добавьте записи для каждого из интерфейсов с [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) макрос или один из его варианты и выполнить сопоставление с [END_COM_MAP](#end_com_map) макрос.

### <a name="example"></a>Пример

Из библиотеки ATL [BEEPER](../../visual-cpp-samples.md) пример:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>  END_COM_MAP

Завершает определение интерфейса COM карты.

```
END_COM_MAP()
```

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)<br/>
[Глобальные функции сопоставления COM](../../atl/reference/com-map-global-functions.md)

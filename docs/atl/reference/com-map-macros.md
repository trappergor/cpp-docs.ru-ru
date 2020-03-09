---
title: Макросы схемы COM
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 3159a53b5a500aa61b85cf2bc5a97d321ed6ebb5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864935"
---
# <a name="com-map-macros"></a>Макросы схемы COM

Эти макросы определяют сопоставления интерфейсов COM.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|Помечает начало записей карты COM-интерфейса.|
|[END_COM_MAP](#end_com_map)|Помечает конец записей карты COM-интерфейса.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="begin_com_map"></a>BEGIN_COM_MAP

Схема COM — это механизм, который предоставляет интерфейсы для объекта клиенту с помощью `QueryInterface`.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя объекта класса, на котором вы предоставляете интерфейсы.

### <a name="remarks"></a>Remarks

[CComObjectRootEx:: интерналкуеринтерфаце](ccomobjectrootex-class.md#internalqueryinterface) Возвращает указатели только для интерфейсов в сопоставлении com. Запустите карту интерфейса с помощью макроса BEGIN_COM_MAP, добавьте записи для каждого интерфейса с помощью макроса [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) или одного из его вариантов и завершите карту с помощью макроса [END_COM_MAP](#end_com_map) .

### <a name="example"></a>Пример

В примере с шаблоном [BEEPER](../../overview/visual-cpp-samples.md) библиотеки ATL:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>END_COM_MAP

Завершает определение карты COM-интерфейса.

```
END_COM_MAP()
```

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[Глобальные функции сопоставления COM](../../atl/reference/com-map-global-functions.md)

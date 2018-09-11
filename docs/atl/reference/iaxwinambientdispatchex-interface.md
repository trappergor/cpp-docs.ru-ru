---
title: Интерфейс IAxWinAmbientDispatchEx | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c1c6ed120705886c1b0bb4836e851139543f629
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753916"
---
# <a name="iaxwinambientdispatchex-interface"></a>Интерфейс IAxWinAmbientDispatchEx

Этот интерфейс реализует Дополнительные внешние свойства для размещаемого элемента управления.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|Этот метод вызывается в дополнение к интерфейс внешнее свойство по умолчанию с помощью определенного пользователем интерфейса.|

## <a name="remarks"></a>Примечания

Включите этот интерфейс в приложениях ATL, статически связанные библиотеки ATL и узел элементов управления ActiveX, особенно элементы управления ActiveX, имеют свойства окружающей среды. Не включая этот интерфейс будет создавать это утверждение: «Возможно, вы забыли идентификатор LIBID передаваемые выполнения»

Этот интерфейс предоставляется элементом управления ActiveX библиотеки ATL, размещение объектов. Является производным от [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` добавляет метод, который позволяет дополнить интерфейс внешнего свойства, предоставляемые ATL с собственным.

[AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) будет пытаться загрузить сведения о типе о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, который содержит код.

При связывании ATL90.dll, **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна в несколько форм, как показано в следующей таблице.

|Тип определения|Файл|
|---------------------|----------|
|IDL|atliface.IDL|
|Библиотеки типов|ATL.dll|
|C++|насколько (также входит в ATLBase.h)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Этот метод вызывается в дополнение к интерфейс внешнее свойство по умолчанию с помощью определенного пользователем интерфейса.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatch*  
Указатель на новый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Когда `SetAmbientDispatch` вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любого свойства или методы, задаваемые для размещенным элементом управления, если эти свойства еще не заданы [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>См. также

[Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)

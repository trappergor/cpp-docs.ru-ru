---
title: Интерфейс IAxWinAmbientDispatchEx
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: 638152d8c49bd20742a586bc665efcdb662b6f3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276098"
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

<xref:System.Windows.Forms.AxHost> будет пытаться загрузить сведения о типе о `IAxWinAmbientDispatch` и `IAxWinAmbientDispatchEx` из библиотеки типов, который содержит код.

При связывании ATL90.dll, **AXHost** загрузит сведения о типе из библиотеки типов в библиотеке DLL.

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для получения дополнительных сведений.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна в несколько форм, как показано в следующей таблице.

|Тип определения|Файл|
|---------------------|----------|
|IDL|atliface.idl|
|Библиотеки типов|ATL.dll|
|C++|насколько (также входит в ATLBase.h)|

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

Этот метод вызывается в дополнение к интерфейс внешнее свойство по умолчанию с помощью определенного пользователем интерфейса.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatch*<br/>
Указатель на новый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Когда `SetAmbientDispatch` вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любого свойства или методы, задаваемые для размещенным элементом управления, если эти свойства еще не заданы [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>См. также

[Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)

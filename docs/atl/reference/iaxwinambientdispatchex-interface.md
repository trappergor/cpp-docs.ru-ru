---
title: Интерфейс Иаксвинамбиентдиспатчекс
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: 3359c17996eb78c3249abc83ff2d439381f209fe
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352990"
---
# <a name="iaxwinambientdispatchex-interface"></a>Интерфейс Иаксвинамбиентдиспатчекс

Этот интерфейс реализует дополнительные свойства окружения для размещенного элемента управления.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[сетамбиентдиспатч](#setambientdispatch)|Этот метод вызывается для дополнения интерфейса внешнего свойства по умолчанию с определяемым пользователем интерфейсом.|

## <a name="remarks"></a>Комментарии

Включите этот интерфейс в приложения ATL, статически связываемые с ATL и ведущими элементами управления ActiveX, особенно элементы управления ActiveX, имеющие внешние свойства. Не включая этот интерфейс, создаст это утверждение: "возможно, вы забыли передать LIBID в CComModule:: init"

Этот интерфейс предоставляется объектами управления ActiveX ATL. Производный [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)от иаксвинамбиентдиспатч `IAxWinAmbientDispatchEx` добавляет метод, который позволяет дополнять интерфейс внешних свойств, предоставляемый библиотекой ATL, одним из собственных.

<xref:System.Windows.Forms.AxHost> попытается загрузить сведения о типе `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` из библиотеки типов, содержащей код, и из нее.

Если вы связываетесь с ATL90.dll, **AxHost** будет загружать сведения о типе из библиотеки типов в библиотеке DLL.

Дополнительные сведения см. [в разделе Размещение элементов управления ActiveX с помощью ATL AxHost](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) .

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в нескольких формах, как показано в следующей таблице.

|Тип определения|Файл|
|---------------------|----------|
|IDL|описана. idl|
|Библиотека типов|ATL.dll|
|C++|описана. h (также входит в ATLBase. h)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> Иаксвинамбиентдиспатчекс:: Сетамбиентдиспатч

Этот метод вызывается для дополнения интерфейса внешнего свойства по умолчанию с определяемым пользователем интерфейсом.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Параметры

*пдиспатч*<br/>
Указатель на новый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Комментарии

Если `SetAmbientDispatch` метод вызывается с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любых свойств или методов, запрашиваемых размещенным элементом управления, если эти свойства еще не предоставлены [иаксвинамбиентдиспатч](../../atl/reference/iaxwinambientdispatch-interface.md).

## <a name="see-also"></a>См. также раздел

[Интерфейс Иаксвинамбиентдиспатч](../../atl/reference/iaxwinambientdispatch-interface.md)

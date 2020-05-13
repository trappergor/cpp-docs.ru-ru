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
ms.openlocfilehash: f4816846801e388619db62998ec979a1100916ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329981"
---
# <a name="iaxwinambientdispatchex-interface"></a>Интерфейс IAxWinAmbientDispatchEx

Этот интерфейс реализует дополнительные окружающие свойства для развлегенного управления.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|Этот метод называется в дополнение к интерфейсу эмбиента по умолчанию с пользовательским интерфейсом.|

## <a name="remarks"></a>Remarks

Включите этот интерфейс в приложения ATL, которые статически связаны с ATL и принимающей ActiveX Controls, особенно ActiveX Controls, которые имеют свойства Ambient. Не включая этот интерфейс будет генерировать это утверждение: "Вы забыли передать LIBID CComModule::Init"

Этот интерфейс подвергается ATL в ActiveX управления хостингобъектов. Произведено из [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` добавляет метод, который позволяет дополнить интерфейс окружающего свойства, предоставляемый ATL с одним из ваших собственных.

<xref:System.Windows.Forms.AxHost>будет пытаться загрузить `IAxWinAmbientDispatch` информацию о типе и `IAxWinAmbientDispatchEx` из библиотеки типов, которая содержит код.

Если вы ссылаетесь на ATL90.dll, **AXHost** загрузит информацию типа из библиотеки типов в DLL.

Более подробную информацию можно узнать [о хостинге ActiveX Controls с помощью ATL AXHost.](../../atl/hosting-activex-controls-using-atl-axhost.md)

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в ряде форм, как показано в следующей таблице.

|Тип определения|Файл|
|---------------------|----------|
|Idl|atliface.idl|
|Тип библиотеки|Atl.dll|
|C++|atliface.h (также включен в ATLBase.h)|

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch

Этот метод называется в дополнение к интерфейсу эмбиента по умолчанию с пользовательским интерфейсом.

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatch*<br/>
Указатель на новый интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

При `SetAmbientDispatch` вызове с указателем на новый интерфейс, этот новый интерфейс будет использоваться для вызова любых свойств или методов, запрошенных хостоутом управления, если эти свойства еще не предоставлены [IAxWinAmbientDispatch.](../../atl/reference/iaxwinambientdispatch-interface.md)

## <a name="see-also"></a>См. также раздел

[Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)

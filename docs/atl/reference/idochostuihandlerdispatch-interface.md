---
title: Интерфейс IDocHostUIHandlerDispatch
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: b7072b80b738aa12635427a2604b38fb3585b452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329726"
---
# <a name="idochostuihandlerdispatch-interface"></a>Интерфейс IDocHostUIHandlerDispatch

Интерфейс для движка Microsoft HTML, разбирающего и рендеринга.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

> [!NOTE]
> Ссылки в следующей таблице относятся к справочным темам INet SDK для членов интерфейса [IDocUIHostHandler.](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) `IDocHostUIHandlerDispatch`имеет ту же `IDocUIHostHandler`функциональность, что `IDocHostUIHandlerDispatch` и с той разницей, что это dispinterface в то время как `IDocUIHostHandler` пользовательский интерфейс.

|||
|-|-|
|[ВключитьModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|Вызывается из MSHTML реализации [IOleInPlaceActiveObject::EnableModeless](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Также называется, когда MSHTML отображает модальный uI.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Вызывается на хост MSHTML, чтобы позволить хостелу заменить объект данных MSHTML.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Вызывается MSHTML, когда он используется в качестве цели падения, чтобы позволить хозяину поставлять альтернативный [IDropTarget.](/windows/win32/api/oleidl/nn-oleidl-idroptarget)|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Вызывается MSHTML для получения интерфейса IDispatch хоста.|
|[ГетхостИнфо](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|Извлекает возможности uI хоста MSHTML.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|Возвращает ключ реестра, под которым MSHTML хранит пользовательские предпочтения.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|Вызывается, когда MSHTML удаляет свои меню и панели инструментов.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|Вызывается из MSHTML реализации [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowАктивировать](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|Вызывается из MSHTML реализации [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|Вызывается из MSHTML реализации [IOleInPlaceActiveObject::ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Вызывается из MSHTML для отображения контекстного меню.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Позволяет хосту заменить меню MSHTML и панели инструментов.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|Вызывается MSHTML, когда [IOleInPlaceActiveObject::TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) или [IOleControlSite::TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) называется.|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Вызов MSHTML, чтобы позволить хосте возможность изменить URL для загрузки.|
|[ОбновлениеUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Уведомляет основное приложение об изменении состояния команды.|

## <a name="remarks"></a>Remarks

Хост может заменить меню, панели инструментов и контекстные меню, используемые движком microsoft HTML для разбора и визуализации (MSHTML) путем реализации этого интерфейса.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|Idl|ATLIFace.idl|
|C++|ATLIFace.h (также включен в ATLBase.h)|

## <a name="see-also"></a>См. также раздел

[IDocUIhostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))

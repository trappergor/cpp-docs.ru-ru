---
title: Интерфейс IDocHostUIHandlerDispatch
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: a60c178eff1e02c3032e792f9a0420dfeab82388
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552170"
---
# <a name="idochostuihandlerdispatch-interface"></a>Интерфейс IDocHostUIHandlerDispatch

Интерфейс для синтаксического анализа Microsoft HTML и механизм визуализации.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

> [!NOTE]
>  Ссылки в следующей таблице являются INet SDK справочных разделов для членов [IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) интерфейс. `IDocHostUIHandlerDispatch` имеет ту же функциональность, что `IDocUIHostHandler`, с той разницей, что `IDocHostUIHandlerDispatch` является disp-интерфейсом, тогда как `IDocUIHostHandler` — это пользовательский интерфейс.

|||
|-|-|
|[EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Также вызывается, когда модальный пользовательский Интерфейс отображает MSHTML.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Вызывается в основном MSHTML, чтобы разрешить основному приложению заменить объект данных MSHTML.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Вызвано MSHTML, при его использовании в качестве целевого объекта перетаскивания, чтобы разрешить основному приложению предоставить альтернативный интерфейс [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Вызывается средой MSHTML для получения интерфейса IDispatch главного приложения.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|Возвращает возможности пользовательского интерфейса, MSHTML узла.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|Возвращает раздел реестра, под которой MSHTML хранятся пользовательские настройки.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|Вызывается, когда MSHTML удаляет его меню и панелей инструментов.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Вызывается из MSHTML, чтобы отобразить контекстное меню.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Позволяет узлу для замены MSHTML меню и панелей инструментов.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|Вызывается средой MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) или [IOleControlSite::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) вызывается.|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Вызывается средой MSHTML, чтобы разрешить основному возможность изменить URL-адрес для загрузки.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Уведомляет основное приложение об изменении состояния команды.|

## <a name="remarks"></a>Примечания

Узел можно заменить меню, панелей инструментов и контекстные меню, используемые анализ Microsoft HTML и механизм визуализации (MSHTML), реализовав этот интерфейс.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна как файл IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Насколько (также входит в ATLBase.h)|

## <a name="see-also"></a>См. также

[IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))

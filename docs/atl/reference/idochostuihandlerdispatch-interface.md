---
title: Интерфейс IDocHostUIHandlerDispatch | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58029305ead376217b589c6dd05c1dc660cd5749
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758648"
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
>  Ссылки в следующей таблице являются INet SDK справочных разделов для членов [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) интерфейс. `IDocHostUIHandlerDispatch` имеет ту же функциональность, что `IDocUIHostHandler`, с той разницей, что `IDocHostUIHandlerDispatch` является disp-интерфейсом, тогда как `IDocUIHostHandler` — это пользовательский интерфейс.

|||
|-|-|
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Также вызывается, когда модальный пользовательский Интерфейс отображает MSHTML.|
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Вызывается в основном MSHTML, чтобы разрешить основному приложению заменить объект данных MSHTML.|
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Вызвано MSHTML, при его использовании в качестве целевого объекта перетаскивания, чтобы разрешить основному приложению предоставить альтернативный интерфейс [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Вызывается средой MSHTML для получения интерфейса IDispatch главного приложения.|
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|Возвращает возможности пользовательского интерфейса, MSHTML узла.|
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Возвращает раздел реестра, под которой MSHTML хранятся пользовательские настройки.|
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|Вызывается, когда MSHTML удаляет его меню и панелей инструментов.|
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|Вызывается из реализации MSHTML [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Вызывается из MSHTML, чтобы отобразить контекстное меню.|
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|Позволяет узлу для замены MSHTML меню и панелей инструментов.|
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|Вызывается средой MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) или [IOleControlSite::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) вызывается.|
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Вызывается средой MSHTML, чтобы разрешить основному возможность изменить URL-адрес для загрузки.|
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Уведомляет основное приложение об изменении состояния команды.|

## <a name="remarks"></a>Примечания

Узел можно заменить меню, панелей инструментов и контекстные меню, используемые анализ Microsoft HTML и механизм визуализации (MSHTML), реализовав этот интерфейс.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна как файл IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Насколько (также входит в ATLBase.h)|

## <a name="see-also"></a>См. также

[IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)


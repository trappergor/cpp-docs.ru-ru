---
title: Интерфейс IAxWinHostWindowLic
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: 561a65702f1d4f57b4db1afc75769ce4cc523c1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329912"
---
# <a name="iaxwinhostwindowlic-interface"></a>Интерфейс IAxWinHostWindowLic

Этот интерфейс предоставляет методы для манипулирования лицензированным управлением и его объектом-хозяином.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[СоздатьControlLic](#createcontrollic)|Создает лицензированный элемент управления и прикрепляет его к объекту-хозяину.|
|[СозданиеControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления, прикрепляет его к объекту-хоста и дополнительно настраивает обработчик событий.|

## <a name="remarks"></a>Remarks

`IAxWinHostWindowLic`наследует от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание лицензированных элементов управления.

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует членов этого интерфейса.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|Idl|ATLIFace.idl|
|C++|ATLIFace.h (также включен в ATLBase.h)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHostWindowLic:CreateControlLic

Создает лицензированный элемент управления, инициализирует его и `hWnd`размещает в окне, идентифицированном .

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*bstrLic*<br/>
(в) BSTR, содержащий ключ лицензии для управления.

### <a name="remarks"></a>Remarks

Смотрите [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) для описания оставшихся параметров и значения возврата.

Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `IAxWinHostWindowLic::CreateControlLic`

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*bstrLic*<br/>
(в) BSTR, содержащий ключ лицензии для управления.

### <a name="remarks"></a>Remarks

Смотрите [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) для описания оставшихся параметров и значения возврата.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `IAxWinHostWindowLic::CreateControlLicEx`

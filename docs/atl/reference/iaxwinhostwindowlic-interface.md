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
ms.openlocfilehash: 791f0e4387a54448ffcf6573cf716c5ba122bcaa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511310"
---
# <a name="iaxwinhostwindowlic-interface"></a>Интерфейс IAxWinHostWindowLic

Этот интерфейс предоставляет методы для управления лицензированный элемент управления и его объект узла.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления и прикрепляет его к объекту узла.|
|[CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления, присоединяет его к объекту узла и при необходимости устанавливает обработчик события.|

## <a name="remarks"></a>Примечания

`IAxWinHostWindowLic` наследует от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание Лицензированные элементы управления.

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, в котором используются члены этого интерфейса.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступна как файл IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|Насколько (также входит в ATLBase.h)|

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

Создает лицензированный элемент управления, инициализирует его и размещает его в окне, идентифицируемый `hWnd`.

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*bstrLic*<br/>
[in] BSTR, содержащий лицензионный ключ для элемента управления.

### <a name="remarks"></a>Примечания

См. в разделе [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) описание оставшихся параметров и возвращаемого значения.

Вызов этого метода эквивалентен вызову [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLic`.

##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

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
[in] BSTR, содержащий лицензионный ключ для элемента управления.

### <a name="remarks"></a>Примечания

См. в разделе [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) описание оставшихся параметров и возвращаемого значения.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `IAxWinHostWindowLic::CreateControlLicEx`.


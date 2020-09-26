---
title: Интерфейс Иаксвинхоствиндовлик
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: d7a63fc63b8abcf8574ea9a2fed2556635dba045
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352951"
---
# <a name="iaxwinhostwindowlic-interface"></a>Интерфейс Иаксвинхоствиндовлик

Этот интерфейс предоставляет методы для манипулирования лицензированным элементом управления и его ведущим объектом.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|Имя|Описание|
|-|-|
|[креатеконтроллик](#createcontrollic)|Создает лицензированный элемент управления и прикрепляет его к объекту узла.|
|[креатеконтроллицекс](#createcontrollicex)|Создает лицензированный элемент управления, присоединяет его к объекту узла и при необходимости настраивает обработчик событий.|

## <a name="remarks"></a>Комментарии

`IAxWinHostWindowLic` наследует от [иаксвинхоствиндов](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, которые поддерживают создание лицензированных элементов управления.

Пример, в котором используются члены этого интерфейса, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) .

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C++, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|IDL|Описана. idl|
|C++|Описана. h (также входит в ATLBase. h)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> Иаксвинхоствиндовлик:: Креатеконтроллик

Создает лицензированный элемент управления, инициализирует его и размещает его в окне, определяемом параметром `hWnd` .

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>Параметры

*бстрлик*<br/>
окне Значение BSTR, содержащее лицензионный ключ для элемента управления.

### <a name="remarks"></a>Комментарии

Описание оставшихся параметров и возвращаемого значения см. в разделе [иаксвинхоствиндов:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) .

Вызов этого метода эквивалентен вызову [иаксвинхоствиндовлик:: креатеконтроллицекс](#createcontrollicex)

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLic` .

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> Иаксвинхоствиндовлик:: Креатеконтроллицекс

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне аналогично [иаксвинхоствиндов:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).

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

*бстрлик*<br/>
окне Значение BSTR, содержащее лицензионный ключ для элемента управления.

### <a name="remarks"></a>Комментарии

Описание оставшихся параметров и возвращаемого значения см. в разделе [иаксвинхоствиндов:: креатеконтролекс](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) .

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLicEx` .

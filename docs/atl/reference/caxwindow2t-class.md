---
title: Класс CAxWindow2T | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d45add5f2133191bc046d72e797a7f8374976d63
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757924"
---
# <a name="caxwindow2t-class"></a>Класс CAxWindow2T

Этот класс содержит методы для работы окно, которое размещает элемент ActiveX, а также имеет поддержку размещения Лицензированные элементы управления ActiveX.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Параметры

*TBase*  
Класс, от которого `CAxWindowT` является производным.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Создает объект `CAxWindow2T`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T::Create](#create)|Создает главное окно.|
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, на котором она размещена в указанном окне и возвращает указатель интерфейса (или указателей) из элемента управления.|
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Статический метод, который извлекает имя класса окна.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T::operator =](#operator_eq)|Назначает HWND в существующий `CAxWindow2T` объекта.|

## <a name="remarks"></a>Примечания

`CAxWindow2T` Предоставляет методы для работы с окном, на котором размещается элемент управления ActiveX. `CAxWindow2T` также имеет поддержку размещения Лицензированные элементы управления ActiveX. Размещение обеспечивается " **AtlAxWinLic80**«, который инкапсулируется `CAxWindow2T`.

Класс `CAxWindow2` реализуется как специализация `CAxWindow2T` класса. Такая специализация объявляется как:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` в разделе документированы элементы [CAxWindow](../../atl/reference/caxwindow-class.md).

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, в котором используются члены этого класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T

Создает объект `CAxWindow2T`.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Параметры

*hWnd*  
Дескриптор существующего окна.

##  <a name="create"></a>  CAxWindow2T::Create

Создает главное окно.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="remarks"></a>Примечания

`CAxWindow2T::Create` вызовы [CWindow::Create](../../atl/reference/cwindow-class.md#create) с LPCTSTR *lpstrWndClass* параметру присвоить класс окна, который обеспечивает размещение элементов управления (`AtlAxWinLic80`).

См. в разделе `CWindow::Create` описание параметров и возвращаемого значения.

**Примечание** Если 0 используется как значение для *MenuOrID* параметр, он должен быть указан как 0U (значение по умолчанию) для предотвращения ошибок компилятора.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::Create`.

##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic

Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Параметры

*bstrLicKey*  
Лицензионный ключ для элемента управления; Значение NULL, если создание nonlicensed элемента управления.

### <a name="remarks"></a>Примечания

См. в разделе [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) описание оставшихся параметров и возвращаемого значения.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLic`.

##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx

Создает лицензированный элемент управления ActiveX, инициализирует его, на котором она размещена в указанном окне и возвращает указатель интерфейса (или указателей) из элемента управления.

```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```

### <a name="parameters"></a>Параметры

*bstrLicKey*  
Лицензионный ключ для элемента управления; Значение NULL, если создание nonlicensed элемента управления.

### <a name="remarks"></a>Примечания

См. в разделе [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) описание оставшихся параметров и возвращаемого значения.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CAxWindow2T::CreateControlLicEx`.

##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName

Извлекает имя класса окна.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окна (`AtlAxWinLic80`), в котором можно лицензиями и nonlicensed элементы управления ActiveX.

##  <a name="operator_eq"></a>  CAxWindow2T::operator =

Назначает HWND в существующий `CAxWindow2T` объекта.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*  
Дескриптор существующего окна.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)   
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)

---
title: Класс CAxWindow2T
ms.date: 11/04/2016
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
ms.openlocfilehash: e29c30e95116ad68d3498f3f8d3231a63c92c0a7
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353068"
---
# <a name="caxwindow2t-class"></a>Класс CAxWindow2T

Этот класс предоставляет методы для управления окном, в котором размещается элемент управления ActiveX, а также поддерживает размещение лицензированных элементов управления ActiveX.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```

#### <a name="parameters"></a>Параметры

*тбасе*<br/>
Класс, от которого `CAxWindowT` наследуется.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Формирует объект `CAxWindow2T`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAxWindow2T:: Create](#create)|Создает главное окно.|
|[CAxWindow2T:: Креатеконтроллик](#createcontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне.|
|[CAxWindow2T:: Креатеконтроллицекс](#createcontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его, размещает его в указанном окне и получает указатель интерфейса (или указатели) из элемента управления.|
|[CAxWindow2T:: Жетвндкласснаме](#getwndclassname)|Статический метод, который получает имя класса окна.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAxWindow2T:: operator =](#operator_eq)|Присваивает HWND существующему `CAxWindow2T` объекту.|

## <a name="remarks"></a>Комментарии

`CAxWindow2T` предоставляет методы для манипуляций с окном, в котором размещается элемент управления ActiveX. `CAxWindow2T` также поддерживает размещение лицензированных элементов управления ActiveX. Размещение обеспечивается " **AtlAxWinLic80**", заключенного в `CAxWindow2T` .

Класс `CAxWindow2` реализуется как специализация `CAxWindow2T` класса. Эта специализация объявляется следующим образом:

`typedef CAxWindow2T <CWindow> CAxWindow2;`

> [!NOTE]
> `CAxWindowT` элементы описаны в разделе [каксвиндов](../../atl/reference/caxwindow-class.md).

Пример, в котором используются члены этого класса, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`TBase`

`CAxWindowT`

`CAxWindow2T`

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

## <a name="caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a> CAxWindow2T::CAxWindow2T

Формирует объект `CAxWindow2T`.

```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего окна.

## <a name="caxwindow2tcreate"></a><a name="create"></a> CAxWindow2T:: Create

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

### <a name="remarks"></a>Комментарии

`CAxWindow2T::Create` вызывает [CWindow:: Create](../../atl/reference/cwindow-class.md#create) с параметром LPCTSTR *лпстрвндкласс* , установленным в класс Window, который предоставляет управление размещением ( `AtlAxWinLic80` ).

`CWindow::Create`Описание параметров и возвращаемое значение см. в разделе.

**Примечание** . Если значение 0 используется в качестве значения параметра *менуорид* , его необходимо указать как 0U (значение по умолчанию), чтобы избежать ошибки компилятора.

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `CAxWindow2T::Create` .

## <a name="caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a> CAxWindow2T:: Креатеконтроллик

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

*бстрликкэй*<br/>
Лицензионный ключ для элемента управления; Значение NULL при создании нелицензированного элемента управления.

### <a name="remarks"></a>Комментарии

Описание оставшихся параметров и возвращаемого значения см. в разделе [каксвиндов:: CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) .

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `CAxWindow2T::CreateControlLic` .

## <a name="caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a> CAxWindow2T:: Креатеконтроллицекс

Создает лицензированный элемент управления ActiveX, инициализирует его, размещает его в указанном окне и получает указатель интерфейса (или указатели) из элемента управления.

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

*бстрликкэй*<br/>
Лицензионный ключ для элемента управления; Значение NULL при создании нелицензированного элемента управления.

### <a name="remarks"></a>Комментарии

Описание оставшихся параметров и возвращаемого значения см. в разделе [каксвиндов:: креатеконтролекс](../../atl/reference/caxwindow-class.md#createcontrolex) .

### <a name="example"></a>Пример

Пример, в котором используется, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `CAxWindow2T::CreateControlLicEx` .

## <a name="caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a> CAxWindow2T:: Жетвндкласснаме

Извлекает имя класса окна.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окна ( `AtlAxWinLic80` ), в котором могут размещаться лицензированные и нелицензированные элементы управления ActiveX.

## <a name="caxwindow2toperator-"></a><a name="operator_eq"></a> CAxWindow2T:: operator =

Присваивает HWND существующему `CAxWindow2T` объекту.

```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего окна.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)

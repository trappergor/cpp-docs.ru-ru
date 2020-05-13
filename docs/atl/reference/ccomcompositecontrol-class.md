---
title: Класс CComCompositeControl
ms.date: 11/04/2016
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: 700a8047ab1fa9df85c8e6530eb3eed5f29bd3d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320808"
---
# <a name="ccomcompositecontrol-class"></a>Класс CComCompositeControl

Этот класс предоставляет методы, необходимые для реализации композитного управления.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать для вашего композитного управления.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|Конструктор.|
|[CComCompositeControl::»CComCompositeControl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Позвоните по этому методу, чтобы посоветовать или не сообщить все элементы управления, размещенные композитным управлением.|
|[CComCompositeControl::CalcExtent](#calcextent)|Вызовите этот метод для расчета размера в единицах HIMETRIC ресурса диалога, используемого для размещения композитного управления.|
|[CComCompositeControl::Создание](#create)|Этот метод называется для создания окна управления для композитного управления.|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Вызовите этот метод, чтобы создать окно управления и посоветуйте любой размещенный элемент управления.|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Вызовите этот метод, чтобы установить цвет фона элемента управления композитом, используя цвет фона контейнера.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|Кисть фона.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|Ручка окна, которая в настоящее время имеет фокус.|

## <a name="remarks"></a>Remarks

Классы, полученные из класса, `CComCompositeControl` наследуют функциональность композитного элемента ActiveX. Элементы управления ActiveX, полученные из `CComCompositeControl` размещаются в стандартном диалоговом окне. Эти типы элементов управления называются композитными элементами управления, поскольку они способны размещать другие элементы управления (родные элементы управления Windows и элементы управления ActiveX).

`CComCompositeControl`идентифицирует ресурс диалога для использования в создании композитного элемента управления, ища перечисленного участника данных в классе детей. IdD-элемент этого класса —детей устанавливается в идентификатор ресурсов ресурса ресурса диалогового ресурса, который будет использоваться в качестве окна элемента управления. Ниже приводится пример члена данных, из `CComCompositeControl` которого должен содержаться класс, полученный из них, чтобы определить ресурс диалога, который будет использоваться для окна элемента управления:

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
> Композитные элементы управления всегда оконные элементы управления, хотя они могут содержать элементы управления без окон.

Элемент управления, `CComCompositeControl`реализованного классом, полученным по умолчанию, встроен в систему. Когда элемент управления получает фокус, вводя в содержащее приложение, последовательное нажатие клавиши TAB приведет к циклированию фокуса через все составные элементы управления, содержащиеся элементы, затем из композитного элемента и далее к следующему элементу в порядке вкладки контейнера. Порядок вкладок размещенных элементов управления определяется ресурсом диалога и определяет порядок, в котором будет происходить табуирование.

> [!NOTE]
> Для того, чтобы ускорители работали должным образом `CComCompositeControl`с, необходимо загрузить таблицу ускорителя, как элемент управления создается, передать ручку и количество ускорителей обратно в [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), и, наконец, уничтожить таблицу, когда управление освобождено.

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ccomcompositecontroladvisesinkmap"></a><a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap

Позвоните по этому методу, чтобы посоветовать или не сообщить все элементы управления, размещенные композитным управлением.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Параметры

*bAdvise*<br/>
Правда, если все элементы управления должны быть рекомендованы; в противном случае ложно.

### <a name="return-value"></a>Возвращаемое значение

|||
|-|-|
|S_OK  |Все элементы управления на карте раковины события были соединены или отключены от источника событий успешно.|
|E_FAIL  |Не все элементы управления на карте раковины события могут быть соединены или отключены от источника событий успешно.|
|E_POINTER  |Эта ошибка обычно указывает на проблему с записью на карте раковины события элемента `IDispEventSimpleImpl` управления или проблему с аргументом шаблона, используемым в или базовом `IDispEventImpl` классе.|
|CONNECT_E_ADVISELIMIT  |Достигнут лимит подключений для точки подключения. Больше подключений она принять не может.|
|CONNECT_E_CANNOTCONNECT  |Раковина не поддерживает интерфейс, требуемый этой точкой соединения.|
|CONNECT_E_NOCONNECTION  |Значение cookie не соответствует действительности соединения. Эта ошибка обычно указывает на проблему с записью на карте раковины события элемента `IDispEventSimpleImpl` управления или проблему с аргументом шаблона, используемым в или базовом `IDispEventImpl` классе.|

### <a name="remarks"></a>Remarks

Базовая реализация этого метода выполняет поиск по записям на карте раковины события. Затем он консультирует или не советует точки соединения к объектам COM, описанным входами в sink-карту события. Этот метод члена также опирается на тот факт, что `IDispEventImpl` полученный класс наследует из одного экземпляра для каждого элемента управления на карте раковины, который должен быть консультирован или несоветует.

## <a name="ccomcompositecontrolcalcextent"></a><a name="calcextent"></a>CComCompositeControl::CalcExtent

Вызовите этот метод для расчета размера в единицах HIMETRIC ресурса диалога, используемого для размещения композитного управления.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>Параметры

*Размер*<br/>
Ссылка на `SIZE` структуру, которая должна быть заполнена этим методом.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент управления размещается в диалоговом поле; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Размер возвращается в параметр *размера.*

## <a name="ccomcompositecontrolcreate"></a><a name="create"></a>CComCompositeControl::Создание

Этот метод называется для создания окна управления для композитного управления.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Ручка к родительскому окну элемента управления.

*rcPos*<br/>
Зарезервировано.

*dwInitParam*<br/>
Данные, которые должны быть переданы в управление во время создания управления. Данные, передаваемые как *dwInitParam,* будут отображаться в качестве параметра LPARAM [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) сообщения, которое будет отправлено в композитный элемент управления при его создании.

### <a name="return-value"></a>Возвращаемое значение

Ручка к недавно созданному композитному диалоговому ящику управления.

### <a name="remarks"></a>Remarks

Этот метод обычно вызывается во время активации элемента управления на месте.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl

Конструктор.

```
CComCompositeControl();
```

### <a name="remarks"></a>Remarks

Инициализирует [CComCompositeControl::m_hbrBackground](#m_hbrbackground) и [CComCompositeControl::m_hWndFocus](#m_hwndfocus) членов данных в NULL.

## <a name="ccomcompositecontrolccomcompositecontrol"></a><a name="dtor"></a>CComCompositeControl::»CComCompositeControl

Деструктор

```
~CComCompositeControl();
```

### <a name="remarks"></a>Remarks

Удаляет фоновый объект, если он существует.

## <a name="ccomcompositecontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow

Вызовите этот метод, чтобы создать окно управления и посоветуйте любые размещенные элементы управления.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>Параметры

*hWndParent*<br/>
Ручка к родительскому окну элемента управления.

*rcPos*<br/>
Прямоугольник положения композитного управления в координатах клиента относительно *hWndParent.*

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в недавно созданный составной диалоговой ящик управления.

### <a name="remarks"></a>Remarks

Этот метод называет [CComCompositeControl::Create](#create) и [CComCompositeControl::AdviseSinkMap](#advisesinkmap).

## <a name="ccomcompositecontrolm_hbrbackground"></a><a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground

Кисть фона.

```
HBRUSH m_hbrBackground;
```

## <a name="ccomcompositecontrolm_hwndfocus"></a><a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus

Ручка окна, которая в настоящее время имеет фокус.

```
HWND m_hWndFocus;
```

## <a name="ccomcompositecontrolsetbackgroundcolorfromambient"></a><a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient

Вызовите этот метод, чтобы установить цвет фона элемента управления композитом, используя цвет фона контейнера.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Основные сведения о составном элементе управления](../../atl/atl-composite-control-fundamentals.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)

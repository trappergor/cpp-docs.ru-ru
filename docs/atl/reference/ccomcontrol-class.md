---
title: Класс Ккомконтрол
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: bf0f64d8c7b8e8a3347e4c0fcad902b9e8a0ecb4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497521"
---
# <a name="ccomcontrol-class"></a>Класс Ккомконтрол

Этот класс предоставляет методы для создания элементов управления ATL и управления ими.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, реализующий элемент управления.

*винбасе*<br/>
Базовый класс, реализующий функции для работы с окнами. По умолчанию используется [квиндовимпл](../../atl/reference/cwindowimpl-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомконтрол:: Ккомконтрол](#ccomcontrol)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомконтрол:: Контролкуеринтерфаце](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[Ккомконтрол:: Креатеконтролвиндов](#createcontrolwindow)|Создает окно для элемента управления.|
|[Ккомконтрол:: Фиреончанжед](#fireonchanged)|Сообщает приемнику контейнера, что свойство элемента управления изменилось.|
|[Ккомконтрол:: Фиреонрекуестедит](#fireonrequestedit)|Уведомляет приемник контейнера о том, что свойство элемента управления собирается измениться и что объект запрашивает приемник, как продолжать.|
|[Ккомконтрол:: MessageBox](#messagebox)|Вызовите этот метод, чтобы создать, отобразить и обработать окно сообщения.|

## <a name="remarks"></a>Примечания

`CComControl`— это набор полезных вспомогательных функций элемента управления и важные элементы данных для элементов управления ATL. При создании стандартного элемента управления или элемента управления DHTML с помощью мастера элементов управления ATL мастер автоматически создает производный класс от `CComControl`. `CComControl`наследует большинство своих методов от [ккомконтролбасе](../../atl/reference/ccomcontrolbase-class.md).

Дополнительные сведения о создании элемента управления см. в [руководстве по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проектов ATL см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).

Демонстрацию `CComControl` методов и элементов данных см. в образце [Circ](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WinBase`

[ккомконтролбасе](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="ccomcontrol"></a>Ккомконтрол:: Ккомконтрол

Конструктор.

```
CComControl();
```

### <a name="remarks"></a>Примечания

Вызывает конструктор [ккомконтролбасе](ccomcontrolbase-class.md#ccomcontrolbase) , передавая `m_hWnd` член данных, наследуемый через [квиндовимпл](../../atl/reference/cwindowimpl-class.md).

##  <a name="controlqueryinterface"></a>Ккомконтрол:: Контролкуеринтерфаце

Извлекает указатель на запрошенный интерфейс.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID запрашиваемого интерфейса.

*ппв*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*, или значение null, если интерфейс не найден.

### <a name="remarks"></a>Примечания

Обрабатывает только интерфейсы в таблице-сопоставлении COM.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

##  <a name="createcontrolwindow"></a>Ккомконтрол:: Креатеконтролвиндов

По умолчанию создает окно для элемента управления путем вызова `CWindowImpl::Create`.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Параметры

*хвндпарент*<br/>
окне Обработайте с родительским или владельцем окном. Необходимо указать допустимый описатель окна. Окно управления ограничено областью родительского окна.

*ркпос*<br/>
окне Начальный размер и расположение создаваемого окна.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если вы хотите сделать что-то, отличное от создания одного окна, например, чтобы создать два окна, одно из которых превращается в панель инструментов для элемента управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

##  <a name="fireonchanged"></a>Ккомконтрол:: Фиреончанжед

Сообщает приемнику контейнера, что свойство элемента управления изменилось.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Параметры

*dispID*<br/>
окне Идентификатор измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если класс элемента управления является производным от [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), этот метод вызывает [кфирепропнотифевент:: фиреончанжед](cfirepropnotifyevent-class.md#fireonchanged) для уведомления всех `IPropertyNotifySink` подключенных интерфейсов об изменении указанного свойства элемента управления. Если класс элемента управления не является производным от `IPropertyNotifySink`, этот метод возвращает значение S_OK.

Этот метод можно вызывать, даже если элемент управления не поддерживает точки подключения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

##  <a name="fireonrequestedit"></a>Ккомконтрол:: Фиреонрекуестедит

Уведомляет приемник контейнера о том, что свойство элемента управления собирается измениться и что объект запрашивает приемник, как продолжать.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Параметры

*dispID*<br/>
окне Идентификатор свойства, которое необходимо изменить.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Если класс элемента управления является производным от [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), этот метод вызывает [кфирепропнотифевент:: фиреонрекуестедит](cfirepropnotifyevent-class.md#fireonrequestedit) для уведомления всех `IPropertyNotifySink` подключенных интерфейсов, которые собирается изменить указанное свойство элемента управления. Если класс элемента управления не является производным от `IPropertyNotifySink`, этот метод возвращает значение S_OK.

Этот метод можно вызывать, даже если элемент управления не поддерживает точки подключения.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

##  <a name="messagebox"></a>Ккомконтрол:: MessageBox

Вызовите этот метод, чтобы создать, отобразить и обработать окно сообщения.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Текст, отображаемый в окне сообщения.

*лпсзкаптион*<br/>
Заголовок диалогового окна. Если значение NULL (по умолчанию), используется заголовок "Error".

*Nуведомления*<br/>
Задает содержимое и поведение диалогового окна. Список различных доступных окон сообщений см. в записи [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) в документации Windows SDK. По умолчанию имеется простая кнопка **ОК** .

### <a name="return-value"></a>Возвращаемое значение

Возвращает целочисленное значение, указывающее одно из значений элементов меню, перечисленных в разделе [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) в документации по Windows SDK.

### <a name="remarks"></a>Примечания

`MessageBox`полезен как во время разработки, так и в качестве простого способа отобразить сообщение об ошибке или предупреждение пользователю.

## <a name="see-also"></a>См. также

[Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Класс CComControlBase](../../atl/reference/ccomcontrolbase-class.md)<br/>
[Класс CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)

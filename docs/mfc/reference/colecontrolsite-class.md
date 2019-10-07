---
title: Класс Колеконтролсите
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 9b9b68a001acdf4b08d9cfc01cc67c43217d9a57
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504307"
---
# <a name="colecontrolsite-class"></a>Класс Колеконтролсите

Обеспечивает поддержку пользовательских интерфейсов клиентских элементов управления.

## <a name="syntax"></a>Синтаксис

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleControlSite::COleControlSite](#colecontrolsite)|Создает объект `COleControlSite`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Колеконтролсите:: Бинддефаултпроперти](#binddefaultproperty)|Привязывает свойство размещенного элемента управления по умолчанию к источнику данных.|
|[COleControlSite::BindProperty](#bindproperty)|Привязывает свойство размещенного элемента управления к источнику данных.|
|[COleControlSite::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|
|[COleControlSite::DestroyControl](#destroycontrol)|Уничтожает размещенный элемент управления.|
|[COleControlSite::DoVerb](#doverb)|Выполняет определенную команду размещенного элемента управления.|
|[COleControlSite::EnableDSC](#enabledsc)|Включает источники данных для сайта элемента управления.|
|[COleControlSite::EnableWindow](#enablewindow)|Включает сайт элемента управления.|
|[COleControlSite::FreezeEvents](#freezeevents)|Указывает, принимает ли сайт управления события.|
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопки по умолчанию для размещенного элемента управления.|
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Возвращает идентификатор элемента управления.|
|[COleControlSite::GetEventIID](#geteventiid)|Получает идентификатор интерфейса события для размещенного элемента управления.|
|[COleControlSite::GetExStyle](#getexstyle)|Извлекает расширенные стили сайта элемента управления.|
|[COleControlSite::GetProperty](#getproperty)|Извлекает конкретное свойство размещенного элемента управления.|
|[COleControlSite::GetStyle](#getstyle)|Извлекает стили сайта элемента управления.|
|[COleControlSite::GetWindowText](#getwindowtext)|Извлекает текст размещенного элемента управления.|
|[COleControlSite::InvokeHelper](#invokehelper)|Вызов определенного метода размещенного элемента управления.|
|[COleControlSite::InvokeHelperV](#invokehelperv)|Вызов определенного метода размещенного элемента управления с переменным списком аргументов.|
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Определяет, является ли элемент управления кнопкой по умолчанию в окне.|
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Проверяет видимое состояние сайта элемента управления.|
|[COleControlSite::ModifyStyle](#modifystyle)|Изменяет текущие расширенные стили сайта элемента управления.|
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Изменяет текущие стили сайта элемента управления.|
|[COleControlSite::MoveWindow](#movewindow)|Изменяет расположение сайта элемента управления.|
|[Колеконтролсите:: Куиккактивате](#quickactivate)|Быстрая активация размещенного элемента управления.|
|[COleControlSite::SafeSetProperty](#safesetproperty)|Задает свойство или метод элемента управления без шанса создания исключения.|
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Задает кнопку по умолчанию в окне.|
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Возвращает идентификатор элемента управления.|
|[COleControlSite::SetFocus](#setfocus)|Устанавливает фокус на управляющий узел.|
|[Колеконтролсите:: SetProperty](#setproperty)|Задает конкретное свойство размещенного элемента управления.|
|[COleControlSite::SetPropertyV](#setpropertyv)|Задает конкретное свойство размещенного элемента управления с переменным списком аргументов.|
|[COleControlSite::SetWindowPos](#setwindowpos)|Задает расположение сайта элемента управления.|
|[COleControlSite::SetWindowText](#setwindowtext)|Задает текст размещенного элемента управления.|
|[COleControlSite::ShowWindow](#showwindow)|Показывает или скрывает узел элемента управления.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Получает сведения о нажатии клавиш и назначенные клавиши для размещаемого элемента управления.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Определяет, является ли размещенный элемент управления безоконным.|
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Содержит сведения об обработке клавиатуры для элемента управления.|
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Файл cookie точки соединения элемента управления.|
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Прочие состояния размещаемого элемента управления.|
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink` Файл cookie элемента управления.|
|[COleControlSite::m_dwStyle](#m_dwstyle)|Стили размещаемого элемента управления.|
|[COleControlSite::m_hWnd](#m_hwnd)|Маркер сайта элемента управления.|
|[COleControlSite::m_iidEvents](#m_iidevents)|Идентификатор интерфейса событий для размещенного элемента управления.|
|[COleControlSite::m_nID](#m_nid)|Идентификатор размещенного элемента управления.|
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Указатель на `IOleInPlaceActiveObject` объект размещенного элемента управления.|
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Контейнер размещенного элемента управления.|
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Указатель на `IOleInPlaceObject` объект размещенного элемента управления.|
|[COleControlSite::m_pObject](#m_pobject)|Указатель на `IOleObjectInterface` интерфейс элемента управления.|
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Указатель на `IOleInPlaceObjectWindowless` интерфейс элемента управления.|
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Указатель на объект окна для размещенного элемента управления.|
|[COleControlSite::m_rect](#m_rect)|Размеры сайта элемента управления.|

## <a name="remarks"></a>Примечания

Эта поддержка является основным средством, с помощью которого внедренный элемент управления ActiveX получает сведения о расположении и экстенте его отображаемого сайта, моникере, пользовательском интерфейсе, его свойствах окружения и других ресурсах, предоставляемых его контейнером. `COleControlSite`полностью реализует интерфейсы [IOleControlSite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite), [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [иолеклиентсите](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink), `IBoundObjectSite`, `INotifyDBEvents`, [IRowsetNotify клиента](../../data/oledb/irowsetnotifyimpl-class.md) . Кроме того, реализуется интерфейс IDispatch (обеспечивающий поддержку внешних свойств и приемников событий).

Чтобы создать сайт элемента управления ActiveX с `COleControlSite`помощью, создайте класс, производный от. `COleControlSite` В классе, производном от контейнера (например, в диалоговом окне), `CWnd::CreateControlSite` переопределяет функцию. `CWnd`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>Требования

**Заголовок:** афксокк. h

##  <a name="binddefaultproperty"></a>Колеконтролсите:: Бинддефаултпроперти

Привязывает свойство простой привязки вызывающего объекта по умолчанию, как отмечено в библиотеке типов, к базовому курсору, определенному в свойствах DataSource, UserName, Password и SQL элемента управления источника данных.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Указывает DISPID свойства в элементе управления с привязкой к данным, который должен быть привязан к элементу управления источника данных.

*втпроп*<br/>
Указывает тип свойства для привязки, например VT_BSTR, VT_VARIANT и т. д.

*сзфиелднаме*<br/>
Задает имя столбца в курсоре, предоставленном элементом управления источника данных, к которому будет привязано свойство.

*пдсквнд*<br/>
Указатель на `CWnd`производный объект, на котором размещен элемент управления источника данных, к которому будет привязано свойство.

### <a name="remarks"></a>Примечания

`CWnd` Объект, для которого вызывается эта функция, должен быть элементом управления с привязкой к данным.

##  <a name="bindproperty"></a>Колеконтролсите:: Биндпроперти

Привязывает свойство простой привязки вызывающего объекта, как отмечено в библиотеке типов, к базовому курсору, определенному в свойствах DataSource, UserName, Password и SQL элемента управления источника данных.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>Параметры

*dwDispId*<br/>
Указывает DISPID свойства в элементе управления с привязкой к данным, который должен быть привязан к элементу управления источника данных.

*пвнддск*<br/>
Указатель на `CWnd`производный объект, на котором размещен элемент управления источника данных, к которому будет привязано свойство.

### <a name="remarks"></a>Примечания

`CWnd` Объект, для которого вызывается эта функция, должен быть элементом управления с привязкой к данным.

##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite

Конструирует новый `COleControlSite` объект.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Параметры

*пктрлконт*<br/>
Указатель на контейнер элемента управления (который представляет окно, в котором размещен элемент управления Ативекс).

### <a name="remarks"></a>Примечания

Эта функция вызывается функцией [коккманажер:: CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) . Дополнительные сведения о настройке создания контейнеров см. в разделе [коккманажер:: createsite](../../mfc/reference/coccmanager-class.md#createsite).

##  <a name="createcontrol"></a>  COleControlSite::CreateControl

Создает элемент управления ActiveX, размещенный в `COleControlSite` объекте.

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>Параметры

*пвндктрл*<br/>
Указатель на объект окна, представляющий элемент управления.

*этому*<br/>
Уникальный идентификатор класса элемента управления.

*лпсзвиндовнаме*<br/>
Указатель на текст, отображаемый в элементе управления. Задает значение свойства Caption (заголовок) винодв или Text (если таковое имеется).

*двстиле*<br/>
Стили Windows. Доступные стили перечислены в разделе **"Примечания** ".

*rect*<br/>
Задает размер и расположение элемента управления. Это может быть либо `CRect` объект, `RECT` либо структура.

*nID*<br/>
Указывает идентификатор дочернего окна элемента управления.

*пперсист*<br/>
Указатель на объект, `CFile` содержащий постоянное состояние для элемента управления. Значение по умолчанию равно NULL, что означает, что элемент управления инициализируется без восстановления состояния из постоянного хранилища. Если значение не равно null, это должен быть указатель на `CFile`производный объект, содержащий постоянные данные элемента управления, в виде потока или хранилища. Эти данные могли быть сохранены в предыдущей активации клиента. Объект `CFile` может содержать другие данные, но его указатель для чтения и записи должен быть установлен на первый байт постоянных данных во время `CreateControl`вызова.

*бстораже*<br/>
Указывает, должны ли данные в *пперсист* интерпретироваться как `IStorage` данные или. `IStream` Если данные в *пперсист* являются хранилищем, *бстораже* должно иметь значение true. Если данные в *пперсист* являются потоком, *бстораже* должен иметь значение false. Значение по умолчанию — FALSE.

*бстрликкэй*<br/>
Необязательные данные лицензионного ключа. Эти данные необходимы только для создания элементов управления, требующих лицензионного ключа во время выполнения. Если элемент управления поддерживает лицензирование, необходимо предоставить лицензионный ключ, чтобы создать элемент управления для выполнения. Значение по умолчанию — NULL.

*PowerPoint*<br/>
Указатель на `POINT` структуру, содержащую левый верхний угол элемента управления. Размер элемента управления определяется значением *псизе*. Значения *PPT* и *псизе* являются необязательным методом указания размера и расположения, из этапов (элемент управления.

*псизе*<br/>
Указатель на `SIZE` структуру, которая содержит размер элемента управления. Левый верхний угол определяется значением *PPT*. Значения *PPT* и *псизе* являются необязательным методом указания размера и расположения, из этапов (элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Поддерживается`CreateControl`только подмножество флагов Windows *двстиле* :

- WS_VISIBLE создает окно, которое изначально видимо. Требуется, если необходимо, чтобы элемент управления был видимым немедленно, например обычным окнам.

- WS_DISABLED создает окно, которое изначально отключено. Отключенное окно не может принимать входные данные от пользователя. Может быть задан, если элемент управления имеет свойство Enabled.

- WS_BORDER создает окно с тонкой линией. Может быть задан, если элемент управления имеет свойство BorderStyle.

- WS_GROUP указывает первый элемент управления группы элементов управления. Пользователь может изменить фокус клавиатуры с одного элемента управления в группе на следующий с помощью клавиш направления. Все элементы управления, определенные с WS_GROUP стилем после первого элемента управления, принадлежат к одной группе. Следующий элемент управления с стилем WS_GROUP завершает группу и запускает следующую группу.

- WS_TABSTOP указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. При нажатии клавиши TAB фокус клавиатуры меняется на следующий элемент управления стиля WS_TABSTOP.

Используйте вторую перегрузку для создания элементов управления размером по умолчанию.

##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl

`COleControlSite` Уничтожает объект.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха; в противном случае — 0

### <a name="remarks"></a>Примечания

После завершения объект освобождается из памяти, и все указатели на этот объект становятся недействительными.

##  <a name="doverb"></a>  COleControlSite::DoVerb

Выполняет указанную команду.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>Параметры

*нверб*<br/>
Задает выполняемую команду. Он может включать один из следующих элементов:

|Значение|Значение|Символ|
|-----------|-------------|------------|
|0|первичный глагол|OLEIVERB_PRIMARY|
|-1|Вторичная команда|(Нет)|
|1|Отображает объект для редактирования.|OLEIVERB_SHOW|
|-2|Редактирует элемент в отдельном окне.|OLEIVERB_OPEN|
|-3|Скрывает объект.|OLEIVERB_HIDE|
|-4|Активирует элемент управления на месте.|OLEIVERB_UIACTIVATE|
|-5|Активирует элемент управления на месте без дополнительных элементов пользовательского интерфейса.|OLEIVERB_INPLACEACTIVATE|
|-7|Отображение свойств элемента управления.|OLEIVERB_PROPERTIES|

*лпмсг*<br/>
Указатель на сообщение, вызвавшее активацию элемента.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция непосредственно вызывается через `IOleObject` интерфейс элемента управления для выполнения указанной команды. Если исключение создается в результате вызова этой функции, возвращается код ошибки HRESULT.

Дополнительные сведения см. в разделе [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

##  <a name="enabledsc"></a>  COleControlSite::EnableDSC

Включает источники данных для сайта управления.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>Примечания

Вызывается платформой для включения и инициализации источников данных для сайта управления. Переопределите эту функцию, чтобы обеспечить настраиваемое поведение.

##  <a name="enablewindow"></a>  COleControlSite::EnableWindow

Включает или отключает ввод с клавиатуры и мыши на управляющий узел.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, следует ли включать или отключать окно: Значение TRUE, если входные данные окна должны быть включены; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно было ранее отключено; в противном случае — 0.

##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents

Указывает, будет ли сайт элемента управления обрабатывать или игнорировать события, инициируемые из элемента управления.

```
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Параметры

*бфризе*<br/>
Указывает, требуется ли остановить прием событий для местоположения элемента управления. Ненулевое значение, если элемент управления не принимает события; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Если *бфризе* имеет значение true, сайт управления запрашивает у элемента управления, чтобы прекращать события. Если *бфризе* имеет значение false, сайт управления запрашивает элемент управления, чтобы продолжить срабатывание событий.

> [!NOTE]
>  Элементу управления не требуется прекращать срабатывание событий, если это запрошено сайтом управления. Он может продолжать обработку, но все последующие события будут игнорироваться сайтом управления.

##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo

Извлекает сведения о назначенных клавишах для элемента управления и клавиатуре.

```
void GetControlInfo();
```

### <a name="remarks"></a>Примечания

Эти сведения хранятся в [колеконтролсите:: m_ctlInfo](#m_ctlinfo).

##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode

Определяет, является ли элемент управления кнопкой по умолчанию.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Возвращаемое значение

Может принимать одно из следующих значений:

- Элемент управления DLGC_DEFPUSHBUTTON является кнопкой по умолчанию в диалоговом окне.

- Элемент управления DLGC_UNDEFPUSHBUTTON не является кнопкой по умолчанию в диалоговом окне.

- элемент управления **0** не является кнопкой.

##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID

Возвращает идентификатор элемента управления.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор элемента диалогового окна элемента управления.

##  <a name="geteventiid"></a>  COleControlSite::GetEventIID

Получает указатель на интерфейс событий элемента управления по умолчанию.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>Параметры

*пиид*<br/>
Указатель на идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха; в противном случае — 0 В случае успеха *пиид* содержит идентификатор интерфейса для интерфейса событий элемента управления по умолчанию.

##  <a name="getexstyle"></a>  COleControlSite::GetExStyle

Получает расширенные стили окна.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расширенные стили окна элемента управления.

### <a name="remarks"></a>Примечания

Чтобы получить обычные стили, вызовите метод [колеконтролсите:: BackStyle](#getstyle).

##  <a name="getproperty"></a>  COleControlSite::GetProperty

Возвращает свойство элемента управления, заданное параметром *двдиспид*.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства, который будет получен в интерфейсе по умолчанию `IDispatch` элемента управления.

*втпроп*<br/>
Указывает тип извлекаемого свойства. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*пвпроп*<br/>
Адрес переменной, которая будет принимать значение свойства. Он должен соответствовать типу, заданному параметром *втпроп*.

### <a name="remarks"></a>Примечания

Значение возвращается через *пвпроп*.

##  <a name="getstyle"></a>  COleControlSite::GetStyle

Извлекает стили сайта элемента управления.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Стили окна.

### <a name="remarks"></a>Примечания

Список возможных значений см. в разделе [стили Windows](../../mfc/reference/styles-used-by-mfc.md#window-styles). Чтобы получить расширенные стили сайта элемента управления, вызовите [колеконтролсите:: жетексстиле](#getexstyle).

##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText

Извлекает текущий текст элемента управления.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
Ссылка на `CString` объект, содержащий текущий текст элемента управления.

### <a name="remarks"></a>Примечания

Если элемент управления поддерживает свойство "заголовок", возвращается это значение. Если свойство "название акции" не поддерживается, возвращается значение для свойства Text.

##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper

Вызывает метод или свойство, заданное параметром *двдиспид*, в контексте, заданном параметром *вфлагс*.

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства или метода, который будет вызываться в `IDispatch` интерфейсе элемента управления.

*вфлагс*<br/>
Флаги, описывающие контекст вызова IDispatch:: Invoke. Возможные значения *вфлагс* см. в `IDispatch::Invoke` разделе Windows SDK.

*втрет*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*пврет*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, заданному параметром *втрет*.

*пбпараминфо*<br/>
Указатель на строку байтов с завершающим нулем, указывающую типы параметров, следующие *пбпараминфо*. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Список переменных параметров типов, указанных в *пбпараминфо*.

### <a name="remarks"></a>Примечания

Параметр *пбпараминфо* задает типы параметров, передаваемых методу или свойству. Список переменных аргументов представлен... в объявлении синтаксиса.

Эта функция преобразует параметры в значения VARIANTARG, а затем вызывает `IDispatch::Invoke` метод для элемента управления. Если вызов `IDispatch::Invoke` завершается сбоем, эта функция создает исключение. Если `IDispatch::Invoke` код состояния `DISP_E_EXCEPTION` ,возвращенный,`COleException`имеет значение, эта функция создает объект,впротивномслучаевызываетисключение.`COleDispatchException`

##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV

Вызывает метод или свойство, заданное параметром *двдиспид*, в контексте, заданном параметром *вфлагс*.

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства или метода, который будет вызываться в `IDispatch` интерфейсе элемента управления.

*вфлагс*<br/>
Флаги, описывающие контекст вызова IDispatch:: Invoke.

*втрет*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*пврет*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, заданному параметром *втрет*.

*пбпараминфо*<br/>
Указатель на строку байтов с завершающим нулем, указывающую типы параметров, следующие *пбпараминфо*. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Указатель на список аргументов переменной.

### <a name="remarks"></a>Примечания

Параметр *пбпараминфо* задает типы параметров, передаваемых методу или свойству. Дополнительные параметры для вызываемого метода или свойства можно передать с помощью параметра *va_list* .

Как правило, эта функция вызывается `COleControlSite::InvokeHelper`методом.

##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton

Определяет, является ли элемент управления кнопкой по умолчанию.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления является кнопкой по умолчанию в окне; в противном случае — ноль.

##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled

Определяет, включен ли сайт управления.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления включен; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Значение извлекается из стандартного свойства, включенного в элемент управления.

##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless

Определяет, является ли объект безоконным элементом управления.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>Примечания

Ненулевое значение, если у элемента управления нет окна; в противном случае — ноль.

##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo

Сведения о том, как ввод с клавиатуры обрабатывается элементом управления.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>Примечания

Эти сведения хранятся в структуре [контролинфо](/windows/win32/api/ocidl/ns-ocidl-controlinfo) .

##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink

Содержит файл cookie точки подключения из приемника событий элемента управления.

```
DWORD m_dwEventSink;
```

##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus

Содержит различные сведения об элементе управления.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [олемиск](/windows/win32/api/oleidl/ne-oleidl-olemisc)в Windows SDK.

##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink

Содержит файл cookie [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) .

```
DWORD m_dwPropNotifySink;
```

##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle

Содержит стили окна элемента управления.

```
DWORD m_dwStyle;
```

##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd

Содержит HWND элемента управления или значение NULL, если элемент управления не является окном.

```
HWND m_hWnd;
```

##  <a name="m_iidevents"></a>Колеконтролсите:: m_iidEvents

Содержит идентификатор интерфейса для интерфейса приемника событий по умолчанию элемента управления.

```
IID m_iidEvents;
```

##  <a name="m_nid"></a>  COleControlSite::m_nID

Содержит идентификатор элемента диалогового окна элемента управления.

```
UINT m_nID;
```

##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject

Содержит интерфейс [метода IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) элемента управления.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont

Содержит контейнер элемента управления (представляющий форму).

```
COleControlContainer* m_pCtrlCont;
```

##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject

Содержит `IOleInPlaceObject` интерфейс [IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) элемента управления.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

##  <a name="m_pobject"></a>  COleControlSite::m_pObject

`IOleObjectInterface` Содержит интерфейс элемента управления.

```
LPOLEOBJECT m_pObject;
```

##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject

Содержит интерфейс `IOleInPlaceObjectWindowless`[IOleInPlaceObjectWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) элемента управления.

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl

Содержит указатель на `CWnd` объект, представляющий сам элемент управления.

```
CWnd* m_pWndCtrl;
```

##  <a name="m_rect"></a>  COleControlSite::m_rect

Содержит границы элемента управления относительно окна контейнера.

```
CRect m_rect;
```

##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle

Изменяет стили элемента управления.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*двремове*<br/>
Стили, которые будут удалены из текущих стилей окна.

*двадд*<br/>
Стили, добавляемые из текущих стилей окна.

*нфлагс*<br/>
Флаги позиционирования окна. Список возможных значений см. в описании функции [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если стили изменяются; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Свойство "склад", включенное в элемент управления, будет изменено в соответствии с параметром для WS_DISABLED. Свойство стиля границы акции элемента управления будет изменено в соответствии с запрошенным параметром для WS_BORDER. Все остальные стили применяются непосредственно к маркеру окна элемента управления, если он имеется.

Изменяет стили окна элемента управления. Добавляемые или удаляемые стили можно объединять с помощью побитового оператора &#124; or (). Сведения о доступных стилях окна см. в описании функции [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK.

Если *нфлагс* имеет ненулевое значение, `ModifyStyle` вызывает функцию `SetWindowPos`Win32 и перерисовывает окно путем объединения *нфлагс* со следующими четырьмя флагами:

- SWP_NOSIZE оставляет текущий размер.

- SWP_NOMOVE оставляет текущую заданное расположение.

- SWP_NOZORDER оставляет текущий Z порядок.

- SWP_NOACTIVATE не активирует окно.

Чтобы изменить расширенные стили окна, вызовите [модифистиликс](#modifystyleex).

##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx

Изменяет расширенные стили элемента управления.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*двремове*<br/>
Расширенные стили, которые будут удалены из текущих стилей окна.

*двадд*<br/>
Расширенные стили, добавляемые из текущих стилей окна.

*нфлагс*<br/>
Флаги позиционирования окна. Список возможных значений см. в описании функции [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если стили изменяются; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Свойство "вид запасов" элемента управления будет изменено в соответствии с параметром для WS_EX_CLIENTEDGE. Все остальные расширенные стили окна применяются непосредственно к маркеру окна элемента управления, если он имеется.

Изменяет расширенные стили окна для объекта сайта элемента управления. Добавляемые или удаляемые стили можно объединять с помощью побитового оператора &#124; or (). Сведения о доступных стилях окна см. в описании функции [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

Если *нфлагс* имеет ненулевое значение, `ModifyStyleEx` вызывает функцию `SetWindowPos`Win32 и перерисовывает окно путем объединения *нфлагс* со следующими четырьмя флагами:

- SWP_NOSIZE оставляет текущий размер.

- SWP_NOMOVE оставляет текущую заданное расположение.

- SWP_NOZORDER оставляет текущий Z порядок.

- SWP_NOACTIVATE не активирует окно.

Чтобы изменить расширенные стили окна, вызовите [модифистиле](#modifystyle).

##  <a name="movewindow"></a>  COleControlSite::MoveWindow

Изменяет расположение элемента управления.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Параметры

*x*<br/>
Новое расположение левой части окна.

*y*<br/>
Новое расположение верхней части окна.

*нвидс*<br/>
Новая ширина окна

*нхеигхт*<br/>
Новая высота окна.

##  <a name="quickactivate"></a>Колеконтролсите:: Куиккактивате

Быстрая активация автономного элемента управления.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если узел элемента управления был активирован; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Эта функция должна вызываться только в том случае, если пользователь переопределяет процесс создания элемента управления.

Методы `IPersist*::Load` и`IPersist*::InitNew` должны вызываться после быстрой активации. Элемент управления должен устанавливать подключения к приемникам контейнера во время быстрой активации. Однако эти соединения не являются активными до `IPersist*::Load` вызова метода или. `IPersist*::InitNew`

##  <a name="safesetproperty"></a>Колеконтролсите:: Сафесетпроперти

Задает свойство элемента управления, заданное параметром *двдиспид*.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства или метода, который находится в `IDispatch` интерфейсе элемента управления, который необходимо задать.

*втпроп*<br/>
Указывает тип свойства, которое необходимо задать. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Единственный параметр типа, указанного параметром *втпроп*.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  В отличие `SetProperty` от `SetPropertyV`и, если возникает ошибка (например, попытка установить несуществующее свойство), исключение не создается.

##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton

Устанавливает элемент управления в качестве кнопки по умолчанию.

```
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*бдефаулт*<br/>
Ненулевое значение, если элемент управления должен стать кнопкой по умолчанию; в противном случае — ноль.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  В элементе управления должен быть установлен бит состояния OLEMISC_ACTSLIKEBUTTON.

##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID

Изменяет значение идентификатора элемента диалогового окна элемента управления.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Новое значение идентификатора.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха предыдущий идентификатор элемента диалогового окна; в противном случае — 0.

### <a name="remarks"></a>Примечания

##  <a name="setfocus"></a>  COleControlSite::SetFocus

Устанавливает фокус на элемент управления.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>Параметры

*лпмсг*<br/>
Указатель на [структуру MSG](/windows/win32/api/winuser/ns-winuser-msg). Эта структура содержит сообщение Windows, запускающее `SetFocus` запрос для элемента управления, содержащегося на текущем сайте элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно, на которое ранее был фокус.

##  <a name="setproperty"></a>Колеконтролсите:: SetProperty

Задает свойство элемента управления, заданное параметром *двдиспид*.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства или метода, который находится в `IDispatch` интерфейсе элемента управления, который необходимо задать.

*втпроп*<br/>
Указывает тип свойства, которое необходимо задать. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*...*<br/>
Единственный параметр типа, указанного параметром *втпроп*.

### <a name="remarks"></a>Примечания

Если `SetProperty` возникает ошибка, возникает исключение.

Тип исключения определяется возвращаемым значением попытки установки свойства или метода. Если возвращаемое значение равно `DISP_E_EXCEPTION` `COleDispatchExcpetion` , создается исключение; в противном `COleException`случае — значение.

##  <a name="setpropertyv"></a>Колеконтролсите:: Сетпропертив

Задает свойство элемента управления, заданное параметром *двдиспид*.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>Параметры

*двдиспид*<br/>
Определяет идентификатор диспетчеризации свойства или метода, который находится в `IDispatch` интерфейсе элемента управления, который необходимо задать.

*втпроп*<br/>
Указывает тип свойства, которое необходимо задать. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).

*argList*<br/>
Указатель на список аргументов.

### <a name="remarks"></a>Примечания

Дополнительные параметры для вызываемого метода или свойства можно пассид с помощью параметра *arg_list* . Если `SetProperty` возникает ошибка, возникает исключение.

Тип исключения определяется возвращаемым значением попытки установки свойства или метода. Если возвращаемое значение равно `DISP_E_EXCEPTION` `COleDispatchExcpetion` , создается исключение; в противном `COleException`случае — значение.

##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos

Задает размер, расположение и Z-порядок для сайта элемента управления.

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*пвндинсертафтер*<br/>
Указатель на окно.

*x*<br/>
Новое расположение левой части окна.

*y*<br/>
Новое расположение верхней части окна.

*cx*<br/>
Новая ширина окна

*CY*<br/>
Новая высота окна.

*нфлагс*<br/>
Задает размер окна и флаги позиционирования. Возможные значения см. в разделе "Примечания" для [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, в противном случае ноль.

##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText

Задает текст для сайта элемента управления.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*лпсзстринг*<br/>
Указатель на строку, завершающуюся нулем и используемую в качестве нового заголовка или текста элемента управления.

### <a name="remarks"></a>Примечания

Сначала эта функция пытается установить свойство "заголовок акции". Если свойство "название акции" не поддерживается, вместо него задается свойство Text.

##  <a name="showwindow"></a>  COleControlSite::ShowWindow

Задает режим отображения окна.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Параметры

*нкмдшов*<br/>
Указывает способ отображения сайта элемента управления. Оно должно иметь одно из следующих значений:

- SW_HIDE Скрывает это окно и передает активацию другому окну.

- SW_MINIMIZE свертывает окно и активирует окно верхнего уровня в системном списке.

- SW_RESTORE активирует и отображает окно. Если окно является сведенным или развернутым, Windows восстанавливает его исходный размер и расположение.

- SW_SHOW активирует окно и отображает его в текущем размере и положении.

- SW_SHOWMAXIMIZED активирует окно и отображает его как развернутое окно.

- SW_SHOWMINIMIZED активирует окно и отображает его в виде значка.

- SW_SHOWMINNOACTIVE отображает окно в виде значка. Активное окно остается активным.

- SW_SHOWNA отображает окно в текущем состоянии. Активное окно остается активным.

- SW_SHOWNOACTIVATE отображает окно в самом последнем размере и положении. Активное окно остается активным.

- SW_SHOWNORMAL активирует и отображает окно. Если окно является сведенным или развернутым, Windows восстанавливает его исходный размер и расположение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно было ранее видимо; 0, если окно ранее было скрыто.

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)

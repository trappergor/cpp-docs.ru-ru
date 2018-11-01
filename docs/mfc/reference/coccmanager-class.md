---
title: Класс COccManager
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: 804db7be4ba796a67042e6772ae4cb631c0c232b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440187"
---
# <a name="coccmanager-class"></a>Класс COccManager

Управляет разными сайтами пользовательского элемента управления, реализованного объектами `COleControlContainer` и `COleControlSite` .

## <a name="syntax"></a>Синтаксис

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|Создает объект `COleContainer`.|
|[COccManager::CreateDlgControls](#createdlgcontrols)|Создает элементы управления ActiveX, размещенных в соответствующих `COleContainer` объекта.|
|[COccManager::CreateSite](#createsite)|Создает объект `COleClientSite`.|
|[COccManager::GetDefBtnCode](#getdefbtncode)|Получает код кнопки по умолчанию.|
|[COccManager::IsDialogMessage](#isdialogmessage)|Определяет целевой объект диалогового окна сообщения.|
|[COccManager::IsLabelControl](#islabelcontrol)|Определяет, является ли указанный элемент управления элемент управления label.|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|Определяет, совпадает ли текущий мнемонический символ мнемонический символ из указанного элемента управления.|
|[COccManager::OnEvent](#onevent)|Предпринимается попытка обработки указанного события.|
|[COccManager::PostCreateDialog](#postcreatedialog)|Освобождает ресурсы, выделенные во время создания диалогового окна.|
|[COccManager::PreCreateDialog](#precreatedialog)|Обрабатывает шаблон диалогового окна для элементов управления ActiveX.|
|[COccManager::SetDefaultButton](#setdefaultbutton)|Переключает состояние по умолчанию указанного элемента управления.|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|Отделяет все существующие элементы управления ActiveX из стандартных элементов управления в указанный шаблон диалогового окна.|

## <a name="remarks"></a>Примечания

Базовый класс, `CNoTrackObject`, недокументированные базовый класс (находится в AFXTLS. H). Предназначен для работы с платформой MFC, классы, производные от `CNoTrackObject` класса будут исключены из обнаружения утечек памяти. Не рекомендуется являются производными непосредственно от `CNoTrackObject`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxocc.h

##  <a name="createcontainer"></a>  COccManager::CreateContainer

Вызывается платформой для создания контейнера элемента управления.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект окна, связанный с контейнером пользовательского сайта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный контейнер; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Дополнительные сведения о создании настраиваемых сайтов см. в разделе [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls

Вызывайте эту функцию для создания элементов управления ActiveX, определяемое *pOccDialogInfo* параметра.

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
Указатель на родительский объект диалогового окна.

*lpszResourceName*<br/>
Имя создаваемого ресурса.

*pOccDialogInfo*<br/>
Указатель на шаблон диалогового окна, используемый для создания объекта диалогового окна.

*lpResource*<br/>
Указатель на ресурс.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления был создан успешно; в противном случае значение равно нулю.

##  <a name="createsite"></a>  COccManager::CreateSite

Вызывается платформой для создания элемента управления сайта, размещенного в контейнере, на которые указывают *pCtrlCont*.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Параметры

*pCtrlCont*<br/>
Указатель на элемент управления контейнера размещения нового элемента управления узла.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный элемент управления сайта.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для создания пользовательского элемента управления сайта, с помощью вашей [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-производного класса.

Каждый контейнер элемента управления можно разместить несколько узлов. Создайте дополнительные сайты с несколькими вызовами в `CreateSite`.

##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode

Вызывайте эту функцию, чтобы определить, является ли элемент управления является кнопкой по умолчанию.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащий элемент управления button.

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

- DLGC_DEFPUSHBUTTON управления является кнопкой по умолчанию в диалоговом окне.

- Элемент управления DLGC_UNDEFPUSHBUTTON не является кнопкой по умолчанию в диалоговом окне.

- **0** управления не является кнопкой.

##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage

Вызывается платформой для определения ли сообщение предназначено для указанного диалогового окна и, если это так, обрабатывает сообщение.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*pWndDlg*<br/>
Указатель на окно намеченный целевой объект сообщения.

*lpMsg*<br/>
Указатель на `MSG` структуру, содержащую сообщения для проверки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обработано; в противном случае значение равно нулю.

### <a name="remarks"></a>Примечания

По умолчанию `IsDialogMessage` — для проверки сообщений клавиатуры и преобразовывать их в выбранные элементы для соответствующее диалоговое окно. Например при нажатии клавиши TAB выбирает следующий элемент управления или группа элементов управления.

Переопределите эту функцию, чтобы обеспечить пользовательское поведение для отправки сообщений на указанное диалоговое окно.

##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl

Вызывайте эту функцию, чтобы определить, является ли указанный элемент управления элемент управления label.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления метки; в противном случае ноль

### <a name="remarks"></a>Примечания

Элемент управления label — это приложения, выступает в качестве метки для любой элемент управления является следующим в порядок.

##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic

Вызывайте эту функцию, чтобы определить, соответствует ли текущий мнемонический символ, представленный элементом управления.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

*lpMsg*<br/>
Указатель на сообщение, содержащее мнемонический символ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если мнемонический символ соответствует элементу управления; в противном случае ноль

### <a name="remarks"></a>Примечания

##  <a name="onevent"></a>  COccManager::OnEvent

Вызывается платформой для обработки указанного события.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*pCmdTarget*<br/>
Указатель на `CCmdTarget` объекта, попытка обработки события

*idCtrl*<br/>
Идентификатор ресурса элемента управления.

*pEvent*<br/>
Обрабатываемое событие.

*pHandlerInfo*<br/>
Если значение не NULL, `OnEvent` заполняет `pTarget` и `pmf` членами `AFX_CMDHANDLERINFO` структуры вместо отправки команды. Как правило этот параметр должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если событие было обработано, в противном случае — нуль.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для настройки процесса обработки событий по умолчанию.

##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog

Вызывается платформой для обработки шаблона диалогового окна для элементов управления ActiveX, перед созданием фактическое диалоговое окно.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO` Структура, содержащая сведения о шаблоне диалогового окна и элементы управления ActiveX, размещенных в диалоговом окне.

*pOrigTemplate*<br/>
Указатель на шаблон диалогового окна для использования в диалоговом окне создания.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогового окна, используемый для создания диалогового окна.

### <a name="remarks"></a>Примечания

Поведение по умолчанию вызывает `SplitDialogTemplate`, определение, если существуют элементы управления ActiveX управляет присутствует и возвращает шаблон результирующий диалогового окна.

Переопределите эту функцию для настройки процесса создания размещение элементов управления ActiveX диалоговое окно.

##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog

Вызывается платформой для освобождения памяти, выделенной для шаблона диалогового окна.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO` Структура, содержащая сведения о шаблоне диалогового окна и элементы управления ActiveX, размещенных в диалоговом окне.

### <a name="remarks"></a>Примечания

Эта память была выделена с помощью вызова `SplitDialogTemplate`и был использован для любой размещенные элементы управления ActiveX, в диалоговом окне.

Переопределите эту функцию для настройки процесса очистки все ресурсы, используемые объектом поле диалогового окна.

##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton

Вызывайте эту функцию, чтобы задать элемент управления как кнопка по умолчанию.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на окно, содержащее элемент управления.

*bПо умолчанию*<br/>
Ненулевое значение, если элемент управления должен стать кнопки по умолчанию; в противном случае значение равно нулю.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Элемент управления должен иметь OLEMISC_ACTSLIKEBUTTON состоянии бит. Дополнительные сведения о флагах OLEMISC, см. в разделе [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) темы в Windows SDK.

##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate

Вызывается платформой для разделения элементов управления ActiveX из стандартных элементов управления диалогового окна.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Параметры

*pTemplate*<br/>
Указатель на шаблон диалогового окна, которое необходимо проверить.

*ppOleDlgItems*<br/>
Список указателей на элементов диалоговых окон, которые являются элементами управления ActiveX.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогового окна, содержащую только те элементы не ActiveX. Если нет элементов управления ActiveX, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Если обнаружены все элементы управления ActiveX, шаблон анализируется и создается новый шаблон, содержащий только не-элементы управления ActiveX. Добавляются элементы управления ActiveX, найденные во время этого процесса *ppOleDlgItems*.

Если в шаблоне нет элементов управления ActiveX, возвращается значение NULL, *.*

> [!NOTE]
>  Память, выделенная для нового шаблона освобождается в `PostCreateDialog` функции.

Переопределите эту функцию для настройки этого процесса.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)<br/>
[Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)

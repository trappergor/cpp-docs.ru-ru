---
title: Класс Коккманажер
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
ms.openlocfilehash: c2a49e3396879e5f1e0864ab5342b57541c6b36c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504491"
---
# <a name="coccmanager-class"></a>Класс Коккманажер

Управляет разными сайтами пользовательского элемента управления, реализованного объектами `COleControlContainer` и `COleControlSite` .

## <a name="syntax"></a>Синтаксис

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Коккманажер:: CreateContainer](#createcontainer)|Создает объект `COleContainer`.|
|[Коккманажер:: Креатедлгконтролс](#createdlgcontrols)|Создает элементы управления ActiveX, размещенные связанным `COleContainer` объектом.|
|[Коккманажер:: CreateSite](#createsite)|Создает объект `COleClientSite`.|
|[Коккманажер:: Жетдефбтнкоде](#getdefbtncode)|Получает код кнопки по умолчанию.|
|[Коккманажер:: Исдиалогмессаже](#isdialogmessage)|Определяет целевой объект сообщения диалогового окна.|
|[Коккманажер:: Ислабелконтрол](#islabelcontrol)|Определяет, является ли указанный элемент управления меткой.|
|[Коккманажер:: Исматчингмнемоник](#ismatchingmnemonic)|Определяет, соответствует ли текущая назначенная клавиша заданному элементу управления.|
|[Коккманажер:: oneven](#onevent)|Пытается выполнить обработку указанного события.|
|[Коккманажер::P Осткреатедиалог](#postcreatedialog)|Освобождает ресурсы, выделенные во время создания диалогового окна.|
|[Коккманажер::P Рекреатедиалог](#precreatedialog)|Обрабатывает шаблон диалогового окна для элементов управления ActiveX.|
|[Коккманажер:: Сетдефаултбуттон](#setdefaultbutton)|Переключает состояние по умолчанию указанного элемента управления.|
|[Коккманажер:: Сплитдиалогтемплате](#splitdialogtemplate)|Отделяет все существующие элементы управления ActiveX от стандартных элементов управления в указанном шаблоне диалогового окна.|

## <a name="remarks"></a>Примечания

Базовый класс `CNoTrackObject`является недокументированным базовым классом (расположенным в афкстлс. H). Классы, наследуемые от `CNoTrackObject` класса, предназначенные для использования в платформе MFC, исключаются из обнаружения утечек памяти. Не рекомендуется наследовать непосредственно от `CNoTrackObject`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>Требования

**Заголовок:** афксокк. h

##  <a name="createcontainer"></a>Коккманажер:: CreateContainer

Вызывается платформой для создания контейнера элемента управления.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на объект окна, связанный с пользовательским контейнером сайта.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный контейнер; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Дополнительные сведения о создании пользовательских сайтов см. в разделе [колеконтролконтаинер:: аттачконтролсите](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite).

##  <a name="createdlgcontrols"></a>Коккманажер:: Креатедлгконтролс

Эта функция вызывается для создания элементов управления ActiveX, заданных параметром *поккдиалогинфо* .

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

*пвндпарент*<br/>
Указатель на родительский объект объекта диалогового окна.

*лпсзресаурценаме*<br/>
Имя создаваемого ресурса.

*поккдиалогинфо*<br/>
Указатель на шаблон диалогового окна, используемый для создания объекта диалогового окна.

*лпресаурце*<br/>
Указатель на ресурс.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления успешно создан; в противном случае — ноль.

##  <a name="createsite"></a>Коккманажер:: CreateSite

Вызывается платформой для создания сайта элемента управления, размещенного в контейнере, на который указывает *пктрлконт*.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>Параметры

*пктрлконт*<br/>
Указатель на контейнер элемента управления, в котором размещается новый сайт элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный узел элемента управления.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы создать пользовательский сайт элемента управления с помощью класса, производного от [колеконтролсите](../../mfc/reference/colecontrolsite-class.md).

Каждый контейнер элементов управления может содержать несколько сайтов. Создание дополнительных сайтов с несколькими вызовами `CreateSite`.

##  <a name="getdefbtncode"></a>Коккманажер:: Жетдефбтнкоде

Вызовите эту функцию, чтобы определить, является ли элемент управления кнопкой по умолчанию.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Объект Window, содержащий элемент управления "Кнопка".

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

- Элемент управления DLGC_DEFPUSHBUTTON является кнопкой по умолчанию в диалоговом окне.

- Элемент управления DLGC_UNDEFPUSHBUTTON не является кнопкой по умолчанию в диалоговом окне.

- элемент управления **0** не является кнопкой.

##  <a name="isdialogmessage"></a>Коккманажер:: Исдиалогмессаже

Вызывается платформой для определения того, предназначено ли сообщение для указанного диалогового окна, и, если это, обрабатывает сообщение.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*пвнддлг*<br/>
Указатель на предполагаемое целевое диалоговое окно сообщения.

*лпмсг*<br/>
Указатель на `MSG` структуру, содержащую сообщение для проверки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обрабатывается; в противном случае — ноль.

### <a name="remarks"></a>Примечания

Поведение по умолчанию `IsDialogMessage` — Проверка сообщений клавиатуры и их преобразование в выделенный фрагмент для соответствующего диалогового окна. Например, при нажатии клавиши TAB выбирается следующий элемент управления или группа элементов управления.

Переопределите эту функцию, чтобы обеспечить пользовательское поведение для сообщений, отправляемых в указанное диалоговое окно.

##  <a name="islabelcontrol"></a>Коккманажер:: Ислабелконтрол

Вызовите эту функцию, чтобы определить, является ли указанный элемент управления Label.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления является меткой; в противном случае ноль

### <a name="remarks"></a>Примечания

Элемент управления "метка" выступает в качестве метки для любого элемента управления, который находится рядом в упорядочении.

##  <a name="ismatchingmnemonic"></a>Коккманажер:: Исматчингмнемоник

Вызовите эту функцию, чтобы определить, соответствует ли текущая назначенная клавиша, представленная элементом управления.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее элемент управления.

*лпмсг*<br/>
Указатель на сообщение, содержащее назначенную клавишу для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если назначенная клавиша соответствует элементу управления; в противном случае ноль

### <a name="remarks"></a>Примечания

##  <a name="onevent"></a>Коккманажер:: oneven

Вызывается платформой для выполнения указанного события.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*пкмдтаржет*<br/>
Указатель на `CCmdTarget` объект, пытающийся выполнить обработку события

*идктрл*<br/>
Идентификатор ресурса элемента управления.

*певент*<br/>
Обрабатываемое событие.

*фандлеринфо*<br/>
Если значение не равно `OnEvent` null, заполняет `pTarget` члены `pmf` `AFX_CMDHANDLERINFO` структуры и вместо диспетчеризации команды. Как правило, этот параметр должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если событие обработано; в противном случае — нуль.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы настроить процесс обработки событий по умолчанию.

##  <a name="precreatedialog"></a>Коккманажер::P Рекреатедиалог

Вызывается платформой для обработки шаблона диалогового окна для элементов управления ActiveX перед созданием фактического диалогового окна.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>Параметры

*поккдиалогинфо*<br/>
`_AFX_OCC_DIALOG_INFO` Структура, содержащая сведения о шаблоне диалогового окна и всех элементах управления ActiveX, размещенных в диалоговом окне.

*поригтемплате*<br/>
Указатель на шаблон диалогового окна, который будет использоваться при создании диалогового окна.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогового окна, используемую для создания диалогового окна.

### <a name="remarks"></a>Примечания

Поведение по умолчанию вызывает метод `SplitDialogTemplate`, определяя, имеются ли элементы управления ActiveX, и возвращает результирующий шаблон диалогового окна.

Переопределите эту функцию, чтобы настроить процесс создания диалогового окна, размещающего элементы управления ActiveX.

##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog

Вызвано платформой для освобождения памяти, выделенной для шаблона диалогового окна.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*поккдиалогинфо*<br/>
`_AFX_OCC_DIALOG_INFO` Структура, содержащая сведения о шаблоне диалогового окна и всех элементах управления ActiveX, размещенных в диалоговом окне.

### <a name="remarks"></a>Примечания

Эта память была выделена вызовом `SplitDialogTemplate`метода и использовался для всех размещенных элементов управления ActiveX в диалоговом окне.

Переопределите эту функцию, чтобы настроить процесс очистки всех ресурсов, используемых объектом диалогового окна.

##  <a name="setdefaultbutton"></a>Коккманажер:: Сетдефаултбуттон

Вызовите эту функцию, чтобы установить элемент управления в качестве кнопки по умолчанию.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указатель на окно, содержащее элемент управления.

*бдефаулт*<br/>
Ненулевое значение, если элемент управления должен стать кнопкой по умолчанию; в противном случае — ноль.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  В элементе управления должен быть установлен бит состояния OLEMISC_ACTSLIKEBUTTON. Дополнительные сведения о флагах ОЛЕМИСК см. в разделе [олемиск](/windows/win32/api/oleidl/ne-oleidl-olemisc) статьи Windows SDK.

##  <a name="splitdialogtemplate"></a>Коккманажер:: Сплитдиалогтемплате

Вызывается структурой для разделения элементов управления ActiveX от общих элементов управления диалогового окна.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>Параметры

*птемплате*<br/>
Указатель на шаблон диалогового окна для изучения.

*пполедлгитемс*<br/>
Список указателей на элементы диалоговых окон, которые являются элементами управления ActiveX.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру шаблона диалогового окна, содержащий только элементы управления, не относящиеся к ActiveX. Если элементы управления ActiveX отсутствуют, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Если найдены какие-либо элементы управления ActiveX, выполняется анализ шаблона и создается новый шаблон, содержащий только элементы управления, не относящиеся к ActiveX. Все элементы управления ActiveX, найденные во время этого процесса, добавляются в *пполедлгитемс*.

Если в шаблоне нет элементов управления ActiveX, возвращается значение NULL *.*

> [!NOTE]
>  Память, выделенная для нового шаблона, освобождается `PostCreateDialog` в функции.

Переопределите эту функцию, чтобы настроить этот процесс.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)<br/>
[Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)

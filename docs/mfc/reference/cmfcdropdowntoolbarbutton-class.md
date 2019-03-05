---
title: Класс CMFCDropDownToolbarButton
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: b33e50328fd3c8997774515f248780edda6bcc75
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275497"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>Класс CMFCDropDownToolbarButton

Тип кнопки панели инструментов, который при нажатии ведет себя как обычная кнопка. Тем не менее, он открывает панель инструментов с раскрывающимся ( [класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md) Если пользователь нажимает и удерживает кнопку панели инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Создает объект `CMFCDropDownToolbarButton`.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Копирует свойства другую кнопку панели инструментов для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Откроется панель инструментов раскрывающегося списка.|
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Копирует текст панели инструментов в меню. (Переопределяет [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Извлекает, связанный с кнопкой панели инструментов раскрывающегося списка.|
|`CMFCDropDownToolbarButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Определяет, является ли в настоящее время открытым раскрывающегося списка на панели инструментов.|
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Определяет, может ли отображаться кнопки с расширенной границей. (Переопределяет [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызывается платформой для обработки [WM_CANCELMODE](/windows/desktop/winmsg/wm-cancelmode) сообщения. (Переопределяет `CMCToolBarButton::OnCancelMode`.)|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Вызывается платформой, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Вызывается платформой, когда пользователь отпускает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Вызывается платформой, когда родительский инструментов обрабатывает сообщение WM_HELPHITTEST. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительского. (Переопределяет [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Вызывается платформой для отрисовки кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается платформой для отрисовки кнопки **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Задает команду по умолчанию, который она используется, когда пользователь нажимает кнопку.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Указывает продолжительность времени, пользователь должен удерживать кнопку мыши до появления панели инструментов выберите в раскрывающемся.|

## <a name="remarks"></a>Примечания

Объект `CMFCDropDownToolBarButton` отличается от обычной кнопки, у нее есть маленькую стрелку в правом нижнем углу кнопку. После того как пользователь выберет кнопки на панели инструментов выберите в раскрывающемся, платформа отображает значок на панели инструментов верхнего уровня (кнопка с маленькую стрелку в правом нижнем углу).

Сведения о том, как реализовать раскрывающемся списке панели инструментов см. в разделе [класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md).

`CMFCDropDownToolBarButton` Объекта могут быть экспортированы в [класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) объекта и отображается как кнопка меню с помощью всплывающего меню.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom

Копирует свойства другую кнопку панели инструментов для текущей кнопки.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Ссылка «источник» из которого необходимо скопировать.

### <a name="remarks"></a>Примечания

Этот метод используется для копирования другую кнопку панели инструментов, чтобы эта кнопка панели инструментов. *src* должен иметь тип `CMFCDropDownToolbarButton`.

##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton

Создает объект `CMFCDropDownToolbarButton`.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
[in] По умолчанию текст кнопки.

*pToolBar*<br/>
[in] Указатель на `CMFCDropDownToolBar` объект, который отображается, когда пользователь нажимает кнопку.

### <a name="remarks"></a>Примечания

Вторая перегрузка конструктора копирует разворачивающейся кнопки первой кнопки на панели инструментов, *pToolBar* указывает.

Как правило, кнопки раскрывающегося списка использует текст из недавно использованных кнопки на панели инструментов, *pToolBar* указывает. Она использует текст, заданный параметром *lpszName* при преобразуется в меню кнопки со стрелкой, или отображается в **команды** вкладке **Настройка** диалоговое окно. Дополнительные сведения о **Настройка** диалоговом окне см. в разделе [класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCDropDownToolbarButton` класса. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar

Откроется панель инструментов раскрывающегося списка.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Родительское окно фрейма раскрывающегося списка, или значение NULL для использования родительского окна, кнопки раскрывающегося списка на панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

[CMFCDropDownToolbarButton::OnClick](#onclick) метод вызывает этот метод, чтобы открыть панель инструментов раскрывающегося списка, когда пользователь нажимает и удерживает кнопку панели инструментов.

Этот метод создает раскрывающегося списка на панели инструментов с помощью [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) метод. Если родительский инструментов закреплено по вертикали, этот метод помещает панели инструментов с раскрывающимся к левой или правой части панели инструментов родительского, в зависимости от соответствия. В противном случае этот метод помещает инструментов раскрывающегося списка под родительской панели инструментов.

Этот метод завершается ошибкой, если *pWnd* имеет значение NULL, и кнопку раскрывающегося списка на панели инструментов не имеет родительского окна.

##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton

Копирует текст панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*MenuButton*<br/>
[in] Ссылка на кнопке меню целевой объект.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод вызывает реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), а затем добавляется к кнопке меню целевого раскрывающееся меню, которое содержит каждый элемент меню панели инструментов в эту кнопку. Этот метод не добавляет подменю во всплывающем меню.

Этот метод завершается ошибкой, если панели родительского `m_pToolBar`, имеет значение NULL или базовая реализация возвращает значение FALSE.

##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar

Извлекает, связанный с кнопкой панели инструментов раскрывающегося списка.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Панель инструментов раскрывающегося списка, связанного с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод возвращает `m_pToolBar` элемент данных.

##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown

Определяет, является ли в настоящее время открытым раскрывающегося списка на панели инструментов.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если в раскрывающемся списке панели инструментов в данный момент открыт; в противном случае 0.

### <a name="remarks"></a>Примечания

Платформа открывает раскрывающегося списка на панели инструментов с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Платформа закрывает панели инструментов с раскрывающимся, когда пользователь нажимает кнопку мыши влево в неклиентской области панели инструментов выберите в раскрывающемся.

##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize

Определяет, может ли отображаться кнопки с расширенной границей.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки панели инструментов могут отображаться с расширенной границей; в противном случае 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о расширенных границы, см. в разделе [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay

Указывает продолжительность времени, пользователь должен удерживать кнопку мыши до появления панели инструментов выберите в раскрывающемся.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Примечания

Задержка измеряется в миллисекундах. Значение по умолчанию — 500. Можно задать другой задержки, изменив значение этого члена общих данных.

##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize

Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, которое отображает кнопки.

*sizeDefault*<br/>
[in] По умолчанию размер кнопки.

*bHorz*<br/>
[in] Состояние закрепления панели инструментов родительского. Этот параметр имеет значение TRUE, если панель закреплена горизонтально или является перемещаемой, или значение FALSE, если по вертикали закрепления панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Объект `SIZE` структура, содержащая размеры кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)), добавив горизонтальный размер размер кнопок ширину стрелку раскрывающегося списка.

##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd

Вызывается платформой при вставке кнопки в панели инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Нового родительского окна.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), сняв текстовую метку ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) и параметр [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) и [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) данные-члены в значение FALSE.

##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick

Вызывается платформой, когда пользователь нажимает кнопку мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Родительское окно кнопки панели инструментов.

*bDelay*<br/>
[in] Значение TRUE, если сообщения должны обрабатываться с задержкой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки обрабатывает сообщение щелкните; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), обновив состояние из раскрывающегося списка на панели инструментов.

Когда пользователь щелкает кнопку панели инструментов, этот метод создает таймер, ожидает длину времени, заданного параметром [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) элемент данных, а затем откроется в раскрывающемся списке панели инструментов с помощью [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Этот метод закрывает панели инструментов с раскрывающимся во второй раз пользователь нажимает кнопку панели инструментов.

##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp

Вызывается платформой, когда пользователь отпускает кнопку мыши.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки обрабатывает сообщение щелкните; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), обновив состояние из раскрывающегося списка на панели инструментов.

Этот метод останавливает таймер раскрывающимся списком, если он активен. Панели инструментов с раскрывающимся закрывается в том случае, если он открыт.

Дополнительные сведения о раскрывающимся списком и раскрывающимся списком таймера, см. в разделе [CMFCDropDownToolbarButton::OnClick](#onclick).

##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp

Вызывается платформой, когда родительский инструментов обрабатывает сообщение WM_HELPHITTEST.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Родительское окно кнопки панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки обрабатывает сообщение справки; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) путем вызова [CMFCDropDownToolbarButton::OnClick](#onclick) метод с *bDelay*значение FALSE. Этот метод возвращает значение, которое возвращается методом [CMFCDropDownToolbarButton::OnClick](#onclick).

Дополнительные сведения о сообщении WM_HELPHITTEST см. в разделе [TN028: Поддержка контекстной справки](../../mfc/tn028-context-sensitive-help-support.md).

##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu

Изменяет предоставленный меню, когда приложение отображает контекстное меню на панели инструментов родительского.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Параметры

*pMenu*<br/>
[in] Меню для настройки.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)), отключив следующие пункты меню:

- **Изображение кнопки копирования**

- **Внешний вид кнопки**

- **Изображение**

- **Text**

- **Изображение и текст**

Переопределите этот метод для изменения в контекстном меню, платформа отображает в режим настройки.

##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw

Вызывается платформой для отрисовки кнопки с использованием указанных стилей и параметров.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, которое отображает кнопки.

*rect*<br/>
[in] Ограничивающий прямоугольник кнопки.

*pImages*<br/>
[in] Коллекция изображениям значков панели инструментов, связанный с кнопкой.

*bHorz*<br/>
[in] Состояние закрепления панели инструментов родительского. Этот параметр имеет значение TRUE, если кнопки закреплена горизонтально и FALSE при закреплении кнопки по вертикали.

*bCustomizeMode*<br/>
[in] Указывает, является ли панель инструментов в режим настройки. Этот параметр является значение TRUE, если панель инструментов находится в режим настройки и FALSE, если панель инструментов не в режим настройки.

*bHighlight*<br/>
[in] Указывает, выделена ли кнопки. Этот параметр является значение TRUE, если кнопка выделена и FALSE, если не остается выделенным, кнопки.

*bDrawBorder*<br/>
[in] Указывает, должен ли отображаться граница кнопки. Этот параметр имеет значение TRUE, если кнопки должно отображать его границы и FALSE, когда кнопки не должна отображаться граница.

*bGrayDisabledButtons*<br/>
[in] Указывает, следует ли затенение кнопок или использовать коллекции изображений отключено. Этот параметр имеет значение TRUE, когда отключенные кнопки должно быть затененную и значение FALSE, когда этот метод следует использовать коллекции изображений отключено.

### <a name="remarks"></a>Примечания

Переопределите этот метод для настройки рисования кнопки панели инструментов.

##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList

Вызывается платформой для отрисовки кнопки **команды** области **Настройка** диалоговое окно.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, которое отображает кнопки.

*rect*<br/>
[in] Ограничивающий прямоугольник кнопки.

*bSelected*<br/>
[in] Указывает, выбран ли кнопки. Если этот параметр имеет значение TRUE, выбранной кнопки. Если этот параметр имеет значение FALSE, не выбранной кнопки.

### <a name="return-value"></a>Возвращаемое значение

Ширина в пикселях, кнопки в заданном контексте устройства.

### <a name="remarks"></a>Примечания

Этот метод вызывается с помощью диалогового окна настройки ( **команды** вкладке) когда кнопки необходим для отображения в поле со списком рисуемого владельцем.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)), изменив имя кнопки текстовую подпись кнопки (то есть значению *lpszName* параметр, который передается конструктору).

##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize

Считывает этот объект из архива или записывает его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
[in] `CArchive` Объект, из которого или сериализации.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) путем сериализации идентификатор ресурса родительского панели инструментов. При загрузке архива ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) возвращает ненулевое значение), этот метод задает `m_pToolBar` член данных на панель инструментов, содержащий идентификатор сериализованного ресурса.

##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand

Задает команду по умолчанию, который она используется, когда пользователь нажимает кнопку.

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать команду по умолчанию, которую платформа выполняет, когда пользователь нажимает кнопку. Элемент с Идентификатором команды, заданные *uiCmd* должны быть расположены на панели инструментов родительского раскрывающегося списка.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)

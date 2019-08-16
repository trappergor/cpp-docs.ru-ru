---
title: Класс Кмфкдропдовнтулбарбуттон
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
ms.openlocfilehash: fcfb521e309463da81d0064451297b3b73610d2f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505320"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>Класс Кмфкдропдовнтулбарбуттон

Тип кнопки панели инструментов, который при нажатии ведет себя как обычная кнопка. Однако он открывает раскрывающуюся панель инструментов ( [класс кмфкдропдовнтулбар](../../mfc/reference/cmfcdropdowntoolbar-class.md) , если пользователь нажимает и удерживает кнопку на панели инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфкдропдовнтулбарбуттон:: Кмфкдропдовнтулбарбуттон](#cmfcdropdowntoolbarbutton)|Создает объект `CMFCDropDownToolbarButton`.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкдропдовнтулбарбуттон:: CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущую кнопку. (Переопределяет [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[Кмфкдропдовнтулбарбуттон::D Ропдовнтулбар](#dropdowntoolbar)|Открывает раскрывающийся список панелей инструментов.|
|[Кмфкдропдовнтулбарбуттон:: Експорттоменубуттон](#exporttomenubutton)|Копирование текста из кнопки панели инструментов в меню. (Переопределяет [CMFCToolBarButton:: експорттоменубуттон](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[Кмфкдропдовнтулбарбуттон:: Жетдропдовнтулбар](#getdropdowntoolbar)|Извлекает раскрывающуюся панель инструментов, связанную с кнопкой.|
|`CMFCDropDownToolbarButton::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкдропдовнтулбарбуттон:: DropDown](#isdropdown)|Определяет, открыта ли раскрывающийся список инструментов в данный момент.|
|[Кмфкдропдовнтулбарбуттон:: Исекстрасизе](#isextrasize)|Определяет, может ли кнопка отображаться с расширенной границей. (Переопределяет [CMFCToolBarButton:: исекстрасизе](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[Кмфкдропдовнтулбарбуттон:: Онкалкулатесизе](#oncalculatesize)|Вызывается платформой для вычисления размера кнопки для указанного контекста устройства и состояния закрепления. (Переопределяет [CMFCToolBarButton:: онкалкулатесизе](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызывается платформой для работы с сообщением [WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode) . (Переопределяет `CMCToolBarButton::OnCancelMode`.)|
|[Кмфкдропдовнтулбарбуттон:: Ончанжепарентвнд](#onchangeparentwnd)|Вызывается структурой при вставке кнопки в новую панель инструментов. (Переопределяет [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[Кмфкдропдовнтулбарбуттон:: OnClick](#onclick)|Вызывается структурой при нажатии пользователем кнопки мыши. (Переопределяет [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[Кмфкдропдовнтулбарбуттон:: Онкликкуп](#onclickup)|Вызывается платформой, когда пользователь отпускает кнопку мыши. (Переопределяет [CMFCToolBarButton:: онкликкуп](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[Кмфкдропдовнтулбарбуттон:: Онконтексселп](#oncontexthelp)|Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_HELPHITTEST. (Переопределяет [CMFCToolBarButton:: онконтексселп](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[Кмфкдропдовнтулбарбуттон:: Онкустомиземену](#oncustomizemenu)|Изменяет указанное меню, когда приложение отображает контекстное меню на родительской панели инструментов. (Переопределяет [CMFCToolBarButton:: онкустомиземену](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[Кмфкдропдовнтулбарбуттон:: OnDraw](#ondraw)|Вызывается платформой для рисования кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[Кмфкдропдовнтулбарбуттон:: Ондравонкустомизелист](#ondrawoncustomizelist)|Вызывается платформой для нарисовании кнопки в области **команды** диалогового окна " **Настройка** ". (Переопределяет [CMFCToolBarButton:: ондравонкустомизелист](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[Кмфкдропдовнтулбарбуттон:: Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[Кмфкдропдовнтулбарбуттон:: Сетдефаулткомманд](#setdefaultcommand)|Задает команду по умолчанию, которую платформа использует при нажатии пользователем кнопки.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[Кмфкдропдовнтулбарбуттон:: m_uiShowBarDelay](#m_uishowbardelay)|Указывает период времени, в течение которого пользователь должен удерживать кнопку мыши вниз до появления раскрывающейся панели инструментов.|

## <a name="remarks"></a>Примечания

В `CMFCDropDownToolBarButton` отличие от обычной кнопки в том, что она имеет маленькую стрелку в правом нижнем углу кнопки. После того как пользователь нажмет кнопку на раскрывающейся панели инструментов, платформа отображает его значок на панели инструментов верхнего уровня (кнопка с маленькой стрелкой в правом нижнем углу).

Сведения о том, как реализовать раскрывающийся список инструментов, см. в разделе [класс кмфкдропдовнтулбар](../../mfc/reference/cmfcdropdowntoolbar-class.md).

Объект можно экспортировать в объект [класса кмфктулбарменубуттон](../../mfc/reference/cmfctoolbarmenubutton-class.md) и отобразить как кнопку меню с всплывающим меню. `CMFCDropDownToolBarButton`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[кмфкдропдовнтулбарбуттон](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

##  <a name="copyfrom"></a>Кмфкдропдовнтулбарбуттон:: CopyFrom

Копирует свойства другой кнопки панели инструментов в текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
окне Ссылка на кнопку источника, из которой производится копирование.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен иметь тип `CMFCDropDownToolbarButton`.

##  <a name="cmfcdropdowntoolbarbutton"></a>Кмфкдропдовнтулбарбуттон:: Кмфкдропдовнтулбарбуттон

Создает объект `CMFCDropDownToolbarButton`.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
окне Текст кнопки по умолчанию.

*птулбар*<br/>
окне Указатель на `CMFCDropDownToolBar` объект, который отображается, когда пользователь нажимает кнопку.

### <a name="remarks"></a>Примечания

Вторая перегрузка конструктора копирует на раскрывающийся список кнопку первой кнопки из панели инструментов, *птулбар* указывает.

Как правило, кнопка с раскрывающимся панелью инструментов использует текст из самой последней использованной кнопки на панели инструментов, *птулбар* указывает. Он использует текст, заданный параметром *лпсзнаме* при преобразовании кнопки в кнопку меню или отображенной на вкладке **команды** диалогового окна **Настройка** . Дополнительные сведения о диалоговом окне « **Настройка** » см. в разделе [класс кмфктулбарскустомизедиалог](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

### <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCDropDownToolbarButton` класса. Этот фрагмент кода является частью демонстрационного [примера Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>Кмфкдропдовнтулбарбуттон::D Ропдовнтулбар

Открывает раскрывающийся список панелей инструментов.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Родительское окно раскрывающегося окна или значение NULL для использования родительского окна кнопки раскрывающейся панели.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Метод [кмфкдропдовнтулбарбуттон:: OnClick](#onclick) вызывает этот метод, чтобы открыть раскрывающийся список инструментов, когда пользователь нажимает и удерживает кнопку панели инструментов.

Этот метод создает раскрывающийся список инструментов с помощью метода [кмфкдропдовнфраме:: Create](../../mfc/reference/cmfcdropdownframe-class.md#create) . Если родительская панель инструментов закреплена по вертикали, этот метод размещает раскрывающийся список панелей инструментов в левой или правой части родительской панели инструментов, в зависимости от размера. В противном случае этот метод размещает раскрывающуюся панель инструментов под родительской панелью инструментов.

Этот метод завершается ошибкой, если *приводится* имеет значение null, а кнопка раскрывающегося списка не имеет родительского окна.

##  <a name="exporttomenubutton"></a>Кмфкдропдовнтулбарбуттон:: Експорттоменубуттон

Копирование текста из кнопки панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*менубуттон*<br/>
окне Ссылка на кнопку целевого меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод вызывает реализацию базового класса ( [CMFCToolBarButton:: експорттоменубуттон](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), а затем добавляет к кнопке целевого меню всплывающее меню, которое содержит каждый элемент меню панели инструментов этой кнопки. Этот метод не добавляет подменю во всплывающее меню.

Этот метод завершается ошибкой, если родительская панель инструментов, `m_pToolBar`, имеет значение null или реализация базового класса возвращает значение false.

##  <a name="getdropdowntoolbar"></a>Кмфкдропдовнтулбарбуттон:: Жетдропдовнтулбар

Извлекает раскрывающуюся панель инструментов, связанную с кнопкой.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Раскрывающийся список инструментов, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод возвращает `m_pToolBar` элемент данных.

##  <a name="isdropdown"></a>Кмфкдропдовнтулбарбуттон:: DropDown

Определяет, открыта ли раскрывающийся список инструментов в данный момент.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если раскрывающаяся панель инструментов открыта в данный момент; в противном случае — 0.

### <a name="remarks"></a>Примечания

Платформа открывает раскрывающийся список инструментов с помощью метода [кмфкдропдовнтулбарбуттон::D ропдовнтулбар](#dropdowntoolbar) . Платформа закрывает раскрывающийся список инструментов, когда пользователь нажимает левую кнопку мыши в неклиентской области на раскрывающейся панели инструментов.

##  <a name="isextrasize"></a>Кмфкдропдовнтулбарбуттон:: Исекстрасизе

Определяет, может ли кнопка отображаться с расширенной границей.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка панели инструментов может отображаться с расширенной границей; в противном случае — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о расширенных границах см. в разделе [CMFCToolBarButton:: исекстрасизе](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

##  <a name="m_uishowbardelay"></a>Кмфкдропдовнтулбарбуттон:: m_uiShowBarDelay

Указывает период времени, в течение которого пользователь должен удерживать кнопку мыши вниз до появления раскрывающейся панели инструментов.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Примечания

Время задержки измеряется в миллисекундах. Значение по умолчанию — 500. Можно задать другую задержку, изменив значение этого общего элемента данных.

##  <a name="oncalculatesize"></a>Кмфкдропдовнтулбарбуттон:: Онкалкулатесизе

Вызывается платформой для вычисления размера кнопки для указанного контекста устройства и состояния закрепления.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Контекст устройства, на котором отображается кнопка.

*сизедефаулт*<br/>
окне Размер по умолчанию для кнопки.

*бхорз*<br/>
окне Состояние закрепления родительской панели инструментов. Этот параметр имеет значение TRUE, если панель инструментов закреплена горизонтально или с плавающей запятой, или FALSE, если панель инструментов закреплена по вертикали.

### <a name="return-value"></a>Возвращаемое значение

`SIZE` Структура, содержащая размеры кнопки в пикселях.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онкалкулатесизе](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)), добавляя ширину стрелки раскрывающегося списка к горизонтальному измерению размера кнопки.

##  <a name="onchangeparentwnd"></a>Кмфкдропдовнтулбарбуттон:: Ончанжепарентвнд

Вызывается структурой при вставке кнопки в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), очистив текстовую метку ( [CMFCToolBarButton:: m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) и настроив [CMFCToolBarButton:: m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) и [CMFCToolBarButton :: m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) Data Members to false.

##  <a name="onclick"></a>Кмфкдропдовнтулбарбуттон:: OnClick

Вызывается структурой при нажатии пользователем кнопки мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Родительское окно кнопки панели инструментов.

*бделай*<br/>
окне Значение TRUE, если сообщение должно обрабатываться с задержкой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка обрабатывает сообщение щелчка; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), обновляя состояние раскрывающейся панели инструментов.

Когда пользователь нажимает кнопку на панели инструментов, этот метод создает таймер, который ожидает продолжительность времени, указанное элементом данных [кмфкдропдовнтулбарбуттон:: m_uiShowBarDelay](#m_uishowbardelay) , а затем открывает раскрывающийся список с помощью [кмфкдропдовнтулбарбуттон ::D метод Ропдовнтулбар](#dropdowntoolbar) . Этот метод закрывает раскрывающийся список на панели инструментов во второй раз, когда пользователь нажимает кнопку на панели инструментов.

##  <a name="onclickup"></a>Кмфкдропдовнтулбарбуттон:: Онкликкуп

Вызывается платформой, когда пользователь отпускает кнопку мыши.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка обрабатывает сообщение щелчка; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [CMFCToolBarButton:: онкликкуп](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), обновляя состояние раскрывающейся панели инструментов.

Этот метод останавливает таймер панели инструментов раскрывающегося списка, если он активен. При открытии раскрывающейся панели инструментов она закрывается.

Дополнительные сведения о раскрывающейся панели инструментов и таймере панели инструментов с раскрывающимся списком см. в разделе [кмфкдропдовнтулбарбуттон:: OnClick](#onclick).

##  <a name="oncontexthelp"></a>Кмфкдропдовнтулбарбуттон:: Онконтексселп

Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_HELPHITTEST.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Родительское окно кнопки панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка обрабатывает сообщение справки; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онконтексселп](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)), вызывая метод [кмфкдропдовнтулбарбуттон:: OnClick](#onclick) с *БДЕЛАЙ* установленным в значение false. Этот метод возвращает значение, возвращаемое функцией [кмфкдропдовнтулбарбуттон:: OnClick](#onclick).

Дополнительные сведения о сообщении WM_HELPHITTEST см. в разделе [TN028: Поддержка](../../mfc/tn028-context-sensitive-help-support.md)контекстно-зависимой справки.

##  <a name="oncustomizemenu"></a>Кмфкдропдовнтулбарбуттон:: Онкустомиземену

Изменяет указанное меню, когда приложение отображает контекстное меню на родительской панели инструментов.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Параметры

*пмену*<br/>
окне Меню для настройки.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онкустомиземену](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)), отключая следующие пункты меню:

- **Изображение для кнопки копирования**

- **Внешний вид кнопки**

- **Изображение**

- **Text**

- **Изображение и текст**

Переопределите этот метод, чтобы изменить контекстное меню, отображаемое платформой в режиме настройки.

##  <a name="ondraw"></a>Кмфкдропдовнтулбарбуттон:: OnDraw

Вызывается платформой для рисования кнопки с использованием указанных стилей и параметров.

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
окне Контекст устройства, на котором отображается кнопка.

*rect*<br/>
окне Ограничивающий прямоугольник кнопки.

*пимажес*<br/>
окне Коллекция изображений панелей инструментов, связанных с кнопкой.

*бхорз*<br/>
окне Состояние закрепления родительской панели инструментов. Этот параметр имеет значение TRUE, если кнопка закреплена по горизонтали, и FALSE, если кнопка закреплена по вертикали.

*бкустомиземоде*<br/>
окне Указывает, находится ли панель инструментов в режиме настройки. Этот параметр имеет значение TRUE, если панель инструментов находится в режиме настройки, и FALSE, если панель инструментов не находится в режиме настройки.

*бхигхлигхт*<br/>
окне Указывает, выделена ли кнопка. Этот параметр имеет значение TRUE, если кнопка выделена, и FALSE, если кнопка не выделена.

*бдравбордер*<br/>
окне Указывает, должна ли кнопка отображать ее границу. Этот параметр имеет значение TRUE, когда кнопка должна отображать ее границу и значение FALSE, если кнопка не должна отображать ее границу.

*бграйдисабледбуттонс*<br/>
окне Указывает, следует ли затенить отключенные кнопки или использовать коллекцию отключенных изображений. Этот параметр имеет значение TRUE, если отключенные кнопки должны быть затенены и FALSE, если этот метод должен использовать коллекцию отключенных изображений.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы настроить рисование на кнопке панели инструментов.

##  <a name="ondrawoncustomizelist"></a>Кмфкдропдовнтулбарбуттон:: Ондравонкустомизелист

Вызывается платформой для нарисовании кнопки в области **команды** диалогового окна " **Настройка** ".

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Контекст устройства, на котором отображается кнопка.

*rect*<br/>
окне Ограничивающий прямоугольник кнопки.

*бселектед*<br/>
окне Выбрана ли кнопка. Если этот параметр имеет значение TRUE, то кнопка выбрана. Если этот параметр имеет значение FALSE, кнопка не выбрана.

### <a name="return-value"></a>Возвращаемое значение

Ширина (в пикселях) кнопки в указанном контексте устройства.

### <a name="remarks"></a>Примечания

Этот метод вызывается диалоговым окном Настройка (вкладка « **команды** »), когда кнопка требуется для отображения в списке владельцем.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: ондравонкустомизелист](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)), изменяя текстовую метку кнопки на имя кнопки (то есть на значение параметра *лпсзнаме* , передаваемое конструктору). ).

##  <a name="serialize"></a>Кмфкдропдовнтулбарбуттон:: Serialize

Считывает этот объект из архива или записывает его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
окне `CArchive` Объект, из которого сериализуется или.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) путем сериализации идентификатора ресурса родительской панели инструментов. При загрузке архива ( [CArchive:: Load](../../mfc/reference/carchive-class.md#isloading) возвращает ненулевое значение) Этот метод устанавливает `m_pToolBar` элемент данных на панель инструментов, содержащую сериализованный идентификатор ресурса.

##  <a name="setdefaultcommand"></a>Кмфкдропдовнтулбарбуттон:: Сетдефаулткомманд

Задает команду по умолчанию, которую платформа использует при нажатии пользователем кнопки.

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор команды по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать команду по умолчанию, выполняемую платформой при нажатии пользователем кнопки. Элемент с ИДЕНТИФИКАТОРом команды, заданным параметром *уикмд* , должен быть расположен в родительской раскрывающейся панели инструментов.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)

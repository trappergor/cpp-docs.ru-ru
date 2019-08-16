---
title: Класс Кмфктулбардатетимектрл
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: 7ab6a240a403e70446ebc1860474f6cb9e1d71e3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504764"
---
# <a name="cmfctoolbardatetimectrl-class"></a>Класс Кмфктулбардатетимектрл

Кнопка на панели инструментов, содержащая элемент управления выбора даты и времени.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфктулбардатетимектрл:: Кмфктулбардатетимектрл](#cmfctoolbardatetimectrl)|Создает объект `CMFCToolBarDateTimeCtrl`.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфктулбардатетимектрл:: Канбестретчед](#canbestretched)|Указывает, может ли пользователь растянуть кнопку во время настройки. (Переопределяет [CMFCToolBarButton:: канбестретчед](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[Кмфктулбардатетимектрл:: CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущую кнопку. (Переопределяет [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Зарезервировано для будущего использования.|
|[CMFCToolBarButton:: Експорттоменубуттон](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Копирование текста из кнопки панели инструментов в меню.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[Кмфктулбардатетимектрл:: Жетбикмд](#getbycmd)|Извлекает из приложения `CMFCToolBarDateTimeCtrl` первый объект с указанным идентификатором команды.|
|[Кмфктулбардатетимектрл:: Жетдатетимектрл](#getdatetimectrl)|Возвращает указатель на элемент управления выбора даты и времени.|
|[Кмфктулбардатетимектрл:: "HWND"](#gethwnd)|Получает маркер окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::-HWND](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфктулбардатетимектрл:: во время](#gettime)|Получает выбранное время из элемента управления выбор даты и времени и помещает его в указанную структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) .|
|[Кмфктулбардатетимектрл:: Жеттимеалл](#gettimeall)|Возвращает выбранное время из кнопки элемента управления "Выбор времени" с указанным ИДЕНТИФИКАТОРом команды.|
|[Кмфктулбардатетимектрл:: Хавехотбордер](#havehotborder)|Определяет, отображается ли граница кнопки, когда пользователь нажимает кнопку. (Переопределяет [CMFCToolBarButton:: хавехотбордер](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[Кмфктулбардатетимектрл:: Нотификомманд](#notifycommand)|Указывает, обрабатывает ли кнопка сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) . (Переопределяет [CMFCToolBarButton:: нотификомманд](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[Кмфктулбардатетимектрл:: Онаддтокустомизепаже](#onaddtocustomizepage)|Вызывается структурой при добавлении кнопки в диалоговое окно " **Настройка** ". (Переопределяет [CMFCToolBarButton:: онаддтокустомизепаже](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для указанного контекста устройства и состояния закрепления. (Переопределяет [CMFCToolBarButton:: онкалкулатесизе](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[Кмфктулбардатетимектрл:: Ончанжепарентвнд](#onchangeparentwnd)|Вызывается структурой при вставке кнопки в новую панель инструментов. (Переопределяет [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[Кмфктулбардатетимектрл:: OnClick](#onclick)|Вызывается платформой, когда пользователь щелкает элемент управления. (Переопределяет [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[Кмфктулбардатетимектрл:: Онктлколор](#onctlcolor)|Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_CTLCOLOR. (Переопределяет [CMFCToolBarButton:: онктлколор](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Вызывается платформой для рисования кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Вызывается платформой для нарисовании кнопки в области **команды** диалогового окна " **Настройка** ". (Переопределяет [CMFCToolBarButton:: ондравонкустомизелист](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[Кмфктулбардатетимектрл:: Онглобалфонтсчанжед](#onglobalfontschanged)|Вызывается платформой при изменении глобального шрифта. (Переопределяет [CMFCToolBarButton:: онглобалфонтсчанжед](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[Кмфктулбардатетимектрл:: OnMove](#onmove)|Вызывается структурой при перемещении родительской панели инструментов. (Переопределяет [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[Кмфктулбардатетимектрл:: onShow](#onshow)|Вызывается структурой, когда кнопка станет видимой или невидимой. (Переопределяет [CMFCToolBarButton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Вызвано структурой при изменении размера или расположения родительской панели инструментов, и это изменение приводит к изменению размера кнопки. (Переопределяет [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[Кмфктулбардатетимектрл:: Онупдатетултип](#onupdatetooltip)|Вызывается структурой, когда родительская панель инструментов обновляет текст подсказки. (Переопределяет [CMFCToolBarButton:: онупдатетултип](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Считывает этот объект из архива или записывает его в архив (переопределяет [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)).|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Задает стиль кнопки панели инструментов. (Переопределяет [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[Кмфктулбардатетимектрл:: SetTime](#settime)|Задает время и дату в элементе управления "Выбор времени".|
|[Кмфктулбардатетимектрл:: Сеттимеалл](#settimeall)|Задает время и дату во всех экземплярах элемента управления "Выбор времени" с указанным ИДЕНТИФИКАТОРом команды.|

## <a name="remarks"></a>Примечания

Пример использования элемента управления выбора даты и времени см. в примере проекта Тулбардатетимепиккер. Дополнительные сведения о добавлении кнопок управления на панели инструментов см. в [разделе Пошаговое руководство. Размещение элементов управления на](../../mfc/walkthrough-putting-controls-on-toolbars.md)панелях инструментов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[кмфктулбардатетимектрл](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкстулбардатетимектрл. h

##  <a name="canbestretched"></a>Кмфктулбардатетимектрл:: Канбестретчед

Указывает, может ли пользователь растянуть кнопку во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию платформа не позволяет пользователю растянуть кнопку на панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: канбестретчед](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопку на панели инструментов даты и времени во время настройки.

##  <a name="cmfctoolbardatetimectrl"></a>Кмфктулбардатетимектрл:: Кмфктулбардатетимектрл

Создает и инициализирует объект [кмфктулбардатетимектрл](../../mfc/reference/cmfctoolbardatetimectrl-class.md) .

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
окне Идентификатор элемента управления.

*иимаже*<br/>
окне Индекс изображения в `CMFCToolBarImages` объекте панели инструментов.

*двстиле*<br/>
окне Стиль `CMFCToolBarDateTimeCtrlImpl` окна, создаваемого при нажатии пользователем кнопки.

*ивидс*<br/>
окне Ширина элемента управления в пикселях.

### <a name="remarks"></a>Примечания

Этот объект инициализируется с системной датой и временем. Стиль окна внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта включает параметр *двстиле* и стили WS_CHILD и WS_VISIBLE. Эти стили нельзя изменить с помощью `CMFCToolBarDateTimeCtrl::SetStyle`. Используйте `SetStyle` для изменения стиля `CMFCToolBarDateTimeCtrl` элемента управления.

### <a name="example"></a>Пример

В следующем примере показано, как создать объект `CMFCToolBarDateTimeCtrl` класса. Этот фрагмент кода является частью [примера средства выбора даты и времени на панели инструментов](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>Кмфктулбардатетимектрл:: CopyFrom

Копирует свойства другой кнопки панели инструментов в текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
окне Ссылка на кнопку источника, из которой производится копирование.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен иметь тип `CMFCToolBarDateTimeCtrl`.

##  <a name="exporttomenubutton"></a>Кмфктулбардатетимектрл:: Експорттоменубуттон

Копирование текста из кнопки панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*менубуттон*<br/>
окне Ссылка на кнопку целевого меню.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: експорттоменубуттон](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), загружая строковый ресурс, связанный с идентификатором команды элемента управления. Дополнительные сведения о строковых ресурсах см. в разделе [CStringT:: лоадстринг](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>Кмфктулбардатетимектрл:: Жетбикмд

Извлекает из приложения `CMFCToolBarDateTimeCtrl` первый объект с указанным идентификатором команды.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор команды для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarDateTimeCtrl` объект в приложении с указанным идентификатором команды или значение null, если ни один из `CMFCToolBarDateTimeCtrl` объектов не имеет указанного идентификатора команды.

### <a name="remarks"></a>Примечания

Этот общий служебный метод используется такими методами, как [кмфктулбардатетимектрл:: сеттимеалл](#settimeall) и [Кмфктулбардатетимектрл:: жеттимеалл](#gettimeall) , для установки или получения времени и даты всех экземпляров элемента управления "Выбор времени" с указанным идентификатором команды.

##  <a name="getdatetimectrl"></a>Кмфктулбардатетимектрл:: Жетдатетимектрл

Возвращает указатель на элемент управления выбора даты и времени.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент управления выбора даты и времени; или значение NULL, если элемент управления не существует.

### <a name="remarks"></a>Примечания

Класс инициализирует `m_pWndDateTime` элемент данных при вставке объектавпанельинструментов.`CMFCToolBarDateTimeCtrl` `CMFCToolBarDateTimeCtrl`

##  <a name="gethwnd"></a>Кмфктулбардатетимектрл:: "HWND"

Получает маркер окна, связанный с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Маркер окна, связанный с кнопкой на панели инструментов даты и времени.

### <a name="remarks"></a>Примечания

Этот метод переопределяет метод [CMFCToolBarButton::](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) WebMethod.

##  <a name="gettime"></a>Кмфктулбардатетимектрл:: во время

Получает выбранное время из связанного элемента управления "Выбор даты и времени" и помещает его в указанную структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) .

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Параметры

*тимедест*<br/>
заполняет В первой перегрузке — объект [класса COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который получит сведения о системном времени. Во второй перегрузке объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , который получит сведения о системном времени.

*птимедест*<br/>
заполняет Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения сведений о системном времени. Не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке ненулевое значение, если время успешно записано в объект [класса COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) ; в противном случае — 0. Во второй и третьей перегрузках возвращаемое значение представляет собой DWORD, равный элементу dwFlag, заданному в структуре [нмдатетимечанже](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) .

### <a name="remarks"></a>Примечания

Метод задает член структуры [Нмдатетимечанже](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) dwFlags, чтобы указать, что для элемента выбора даты и времени задано значение даты и времени. Если значение равно GDT_NONE, для `no date` элемента управления задается состояние и используется стиль DTS_SHOWNONE. Если возвращенное значение равно GDT_VALID, системное время успешно хранится в целевом расположении.

##  <a name="gettimeall"></a>Кмфктулбардатетимектрл:: Жеттимеалл

Возвращает время, выбранное пользователем с помощью кнопки элемента управления "Выбор времени" с указанным ИДЕНТИФИКАТОРом команды.

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Задает идентификатор команды для кнопки панели инструментов.

*тимедест*<br/>
заполняет В первой перегрузке — объект [класса COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который получит сведения о системном времени. Во второй перегрузке объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , который получит сведения о системном времени.

*птимедест*<br/>
заполняет Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения сведений о системном времени. Не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Если платформе не удается найти кнопку на панели инструментов, совпадающую с ИДЕНТИФИКАТОРом команды *уикмд*, то возвращаемое значение равно нулю в первой перегрузке и GDT_NONE в других перегрузках. Если кнопка панели инструментов найдена, возвращаемое значение совпадает с возвращаемым значением из вызова [кмфктулбардатетимектрл::-Time](#gettime) на этой кнопке. Возвращаемое значение, равное нулю или GDT_NONE, может возникать при обнаружении кнопки, что означает, `GetTime` что вызов не возвращал допустимой даты по какой-либо другой причине.

### <a name="remarks"></a>Примечания

Этот метод выполняет поиск кнопки на панели инструментов с указанным ИДЕНТИФИКАТОРом команды и вызывает метод [кмфктулбардатетимектрл::-Time](#gettime) для этой кнопки.

##  <a name="havehotborder"></a>Кмфктулбардатетимектрл:: Хавехотбордер

Определяет, отображается ли граница кнопки, когда пользователь нажимает кнопку.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если при выборе кнопки отображается ее граница. в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает ненулевое значение, если элемент управления является видимым.

##  <a name="notifycommand"></a>Кмфктулбардатетимектрл:: Нотификомманд

Указывает, обрабатывает ли кнопка сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) .

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*инотификоде*<br/>
окне Сообщение уведомления, связанное с командой.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка обрабатывает сообщение WM_COMMAND, или значение FALSE, чтобы указать, что сообщение должно обрабатываться родительской панелью инструментов.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, когда отправляет сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) в родительское окно.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: нотификомманд](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) путем обработки уведомления [DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange) . Он обновляет внутреннее состояние времени и обновляет свойство Time всех `CMFCToolBarDateTimeCtrl` объектов с одинаковым идентификатором команды.

##  <a name="onaddtocustomizepage"></a>Кмфктулбардатетимектрл:: Онаддтокустомизепаже

Вызывается структурой при добавлении кнопки в диалоговое окно " **Настройка** ".

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [CMFCToolBarButton:: онаддтокустомизепаже](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), копируя свойства из первого элемента управления даты и времени на любую панель инструментов, которая имеет тот же идентификатор команды, что и этот объект. Этот метод не выполняет никаких действий, если ни одна панель инструментов не имеет элемента управления даты и времени, имеющего тот же идентификатор команды, что и этот объект.

Дополнительные сведения о диалоговом окне « **Настройка** » см. в разделе [класс кмфктулбарскустомизедиалог](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>Кмфктулбардатетимектрл:: Ончанжепарентвнд

Вызывается структурой при вставке кнопки в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) путем повторного создания внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onclick"></a>Кмфктулбардатетимектрл:: OnClick

Вызывается платформой, когда пользователь щелкает элемент управления.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Использующ.

*бделай*<br/>
окне Использующ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка обрабатывает сообщение щелчка; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), возвращая ненулевое значение, если внутренний `CMFCToolBarDateTimeCtrlImpl` объект является видимым.

##  <a name="onctlcolor"></a>Кмфктулбардатетимектрл:: Онктлколор

Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_CTLCOLOR.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Контекст устройства, на котором отображается кнопка.

*нктлколор*<br/>
окне Использующ.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор глобальной кисти, используемой платформой для рисования фона кнопки.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [CMFCToolBarButton:: онктлколор](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), устанавливая цвет текста и фона предоставленного контекста устройства в глобальный текст и цвета фона соответственно.

Дополнительные сведения о глобальных параметрах, доступных для приложения, см. в разделе [Структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>Кмфктулбардатетимектрл:: Онглобалфонтсчанжед

Вызывается платформой при изменении глобального шрифта.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онглобалфонтсчанжед](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)), изменяя шрифт элемента управления на цвет из глобального шрифта.

Дополнительные сведения о глобальных параметрах, доступных для приложения, см. в разделе [Структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>Кмфктулбардатетимектрл:: OnMove

Вызывается структурой при перемещении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновляя положение внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onshow"></a>Кмфктулбардатетимектрл:: onShow

Вызывается структурой, когда кнопка станет видимой или невидимой.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
окне Указывает, является ли кнопка видимой. Если этот параметр имеет значение TRUE, кнопка является видимой. В противном случае кнопка не отображается.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)onShow), отображая кнопку, если *БШОВ* имеет значение true. В противном случае этот метод скрывает кнопку.

##  <a name="onsize"></a>Кмфктулбардатетимектрл:: OnSize

Вызвано структурой при изменении размера или расположения родительской панели инструментов, и это изменение приводит к изменению размера кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*исизе*<br/>
окне Новая ширина кнопки в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)), обновляя размер и расположение внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onupdatetooltip"></a>Кмфктулбардатетимектрл:: Онупдатетултип

Вызывается структурой, когда родительская панель инструментов обновляет текст подсказки.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Родительское окно.

*ибуттониндекс*<br/>
окне Отсчитываемый от нуля индекс кнопки в родительской коллекции кнопок.

*вндтултип*<br/>
окне Элемент управления, отображающий текст подсказки.

*str*<br/>
заполняет `CString` Объект, получающий обновленный текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод обновляет текст подсказки; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онупдатетултип](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, связанный с кнопкой. Если кнопка не закреплена по горизонтали, этот метод не выполняет никаких действий и возвращает значение FALSE.

##  <a name="settime"></a>Кмфктулбардатетимектрл:: SetTime

Задает время и дату в элементе управления "Выбор времени".

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Параметры

*тименев*<br/>
окне В первой версии — ссылка на объект [класса COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий время, в которое будет задаваться элемент управления. Во второй версии — указатель на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий время, в которое будет задаваться элемент управления.

*птименев*<br/>
окне Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которая содержит время, в которое будет задаваться элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Задает время в элементе управления выбора даты и времени путем вызова [CDateTimeCtrl:: setTime](../../mfc/reference/cdatetimectrl-class.md#settime).

##  <a name="settimeall"></a>Кмфктулбардатетимектрл:: Сеттимеалл

Задает время и дату во всех экземплярах элемента управления "Выбор времени" с указанным ИДЕНТИФИКАТОРом команды.

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Задает идентификатор команды для кнопки панели инструментов.

*тименев*<br/>
окне В первой версии — объект [класса COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который содержит время, в которое будет задаваться элемент управления. Во второй версии — указатель на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий время, в которое будет задаваться элемент управления.

*птименев*<br/>
окне Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которая содержит время, в которое будет задаваться элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Выполняет поиск кнопки на панели инструментов с указанным ИДЕНТИФИКАТОРом команды и задает время в элементе управления выбора даты и времени путем вызова [кмфктулбардатетимектрл:: setTime](#settime).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)

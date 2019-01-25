---
title: Класс CMFCToolBarDateTimeCtrl
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
ms.openlocfilehash: 1252f97a93e67348a00c9809e3f216d4ed63c4d8
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893686"
---
# <a name="cmfctoolbardatetimectrl-class"></a>Класс CMFCToolBarDateTimeCtrl

Кнопка панели инструментов, которая содержит элемент управления выбора даты и времени.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Создает объект `CMFCToolBarDateTimeCtrl`.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Указывает, может ли пользователь растянуть кнопки во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Копирует свойства другую кнопку панели инструментов для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Зарезервировано для будущего использования.|
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Копирует текст панели инструментов в меню.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении с указанным идентификатором команды.|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Возвращает указатель на элемент управления выбора даты и времени.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Извлекает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Получает установленный период времени из элемент выбора даты и времени и помещает его в указанном [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуры.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Возвращает установленный период времени с помощью элемента управления кнопки выбора времени с указанным идентификатором команды.|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Определяет, отображается ли граница кнопки, когда пользователь выбирает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщения. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Вызывается платформой, когда пользователь щелкает элемент управления. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Вызывается платформой, когда родительский инструментов обрабатывает wm_ctlcolor-сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|Вызывается платформой для отрисовки кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Вызывается платформой для отрисовки кнопки **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается платформой при изменении глобального шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Вызывается платформой при перемещении родительской панели инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Вызывается платформой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|Вызывается платформой при панели родительского изменении ее размера или положения и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Вызывается платформой, когда родительский инструментов обновляет его текст подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|Считывает этот объект из архива или записывает его в архив (переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|Задает стиль кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Задает дату и время в элементе управления.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Задает дату и время во всех экземплярах элемента управления выбора времени, с указанным идентификатором команды.|

## <a name="remarks"></a>Примечания

Пример того, как использовать элемент управления выбора даты и времени см. в разделе ToolbarDateTimePicker примера проекта. Сведения о том, как добавление кнопок на панели инструментов, см. в разделе [Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbardatetimectrl.h

##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched

Указывает, может ли пользователь растянуть кнопки во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию платформа позволяет пользователю выполнить растяжение кнопки панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопки панели инструментов даты и времени во время настройки.

##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl

Создает и инициализирует [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) объекта.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
[in] Идентификатор элемента управления.

*iImage*<br/>
[in] Индекс изображения в панели инструментов `CMFCToolBarImages` объекта.

*dwStyle*<br/>
[in] Стиль `CMFCToolBarDateTimeCtrlImpl` окно, которое создается, когда пользователь нажимает кнопку.

*iWidth*<br/>
[in] Ширина элемента управления в пикселях.

### <a name="remarks"></a>Примечания

Этот объект инициализируется системной даты и времени. Стиль окна внутреннего `CMFCToolBarDateTimeCtrlImpl` объект включает *dwStyle* параметр и стили WS_CHILD и WS_VISIBLE. Нельзя изменить с помощью этих стилей `CMFCToolBarDateTimeCtrl::SetStyle`. Используйте `SetStyle` Чтобы изменить стиль `CMFCToolBarDateTimeCtrl` элемента управления.

### <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCToolBarDateTimeCtrl` класса. Этот фрагмент кода является частью [пример Выбор инструментов даты / времени](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom

Копирует свойства другую кнопку панели инструментов для текущей кнопки.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Ссылка «источник» из которого необходимо скопировать.

### <a name="remarks"></a>Примечания

Этот метод используется для копирования другую кнопку панели инструментов, чтобы эта кнопка панели инструментов. *src* должен иметь тип `CMFCToolBarDateTimeCtrl`.

##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton

Копирует текст панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*MenuButton*<br/>
[in] Ссылка на кнопке меню целевой объект.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), загрузив строковый ресурс, связанный с Идентификатором команды элемента управления. Дополнительные сведения о строковых ресурсов см. в разделе [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).

##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd

Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении с указанным идентификатором команды.

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды для получения кнопки.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarDateTimeCtrl` объект в приложении, имеющий заданный идентификатор команды, или значение NULL, если не `CMFCToolBarDateTimeCtrl` объекты имеют идентификатор указанной команды.

### <a name="remarks"></a>Примечания

Этот метод служебной программы используется методами, такими как [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) и [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) для задания или получения время и дату, время всех экземпляров Средство выбора элемента управления с указанным идентификатором команды.

##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

Возвращает указатель на элемент управления выбора даты и времени.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на управления выбора даты и времени; или значение NULL, если элемент управления не существует.

### <a name="remarks"></a>Примечания

`CMFCToolBarDateTimeCtrl` Класса инициализирует `m_pWndDateTime` элемент данных при вставке `CMFCToolBarDateTimeCtrl` объекта в панели инструментов.

##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd

Извлекает дескриптор окна, связанный с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор окна, связанный с кнопкой панели инструментов даты и времени.

### <a name="remarks"></a>Примечания

Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод.

##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime

Получает установленный период времени из соответствующую дату и время средства выбора и помещает его в указанном [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуры

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Параметры

*timeDest*<br/>
[out] В первой перегрузке [класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, который будет получать сведения о времени системы. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, который будет получать сведения о времени системы.

*pTimeDest*<br/>
[out] Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру для получения сведения о времени системы. Не должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

В первой перегрузке, ненулевое значение, если время успешно записан [класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта; в противном случае — значение 0. В перегрузках второй и третий, возвращается значение типа DWORD, равное dwFlag член, который был задан в [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) структуры.

### <a name="remarks"></a>Примечания

Метода задает [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) структуры член dwFlags, чтобы указать, имеет ли средство выбора даты и времени значение даты и времени. Если значение равно GDT_NONE, элемент управления имеет значение `no date` состояние и использует стиль DTS_SHOWNONE. Если возвращаемое значение равно GDT_VALID, системное время успешно сохранены в месте назначения.

##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll

Возвращает время, выбранного пользователем с помощью элемента управления кнопки выбора времени с указанным идентификатором команды.

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

*uiCmd*<br/>
[in] Указывает идентификатор команды кнопки панели инструментов.

*timeDest*<br/>
[out] В первой перегрузке [класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, который будет получать сведения о времени системы. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, который будет получать сведения о времени системы.

*pTimeDest*<br/>
[out] Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру для получения сведения о времени системы. Не должен иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Если платформа не удается найти кнопку панели инструментов, соответствующий Идентификатору команды *uiCmd*, возвращаемое значение равно нулю в первой перегрузке и GDT_NONE в других перегрузок. При обнаружении кнопки панели инструментов, возвращаемое значение является таким же, как возвращаемое значение из вызова [CMFCToolBarDateTimeCtrl::GetTime](#gettime) этой кнопки. Возвращаемое значение из нуля или GDT_NONE возникает, когда найден кнопки, которое указывает, что вызов `GetTime` не возвратил допустимую дату по другой причине.

### <a name="remarks"></a>Примечания

Этот метод ищет кнопку панели инструментов, имеющий заданный идентификатор команды и вызовы [CMFCToolBarDateTimeCtrl::GetTime](#gettime) метод этой кнопки.

##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder

Определяет, отображается ли граница кнопки, когда пользователь выбирает кнопку.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка отображает граница при выборе; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает ненулевое значение, если элемент управления является видимым.

##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand

Указывает, обрабатывает ли кнопки [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщения.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*iNotifyCode*<br/>
[in] Сообщение уведомления, который связан с командой.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопки обрабатывает сообщение WM_COMMAND, или FALSE для указания, что сообщения должны обрабатываться родительской панели инструментов.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда он собирается отправить [WM_COMMAND](/windows/desktop/menurc/wm-command) родительское окно.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [DTN_DATETIMECHANGE](/windows/desktop/Controls/dtn-datetimechange) уведомлений. Он обновляет состояние внутреннее время и обновляет свойство времени всех `CMFCToolBarDateTimeCtrl` объекты с тем же команды идентификатор.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage

Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), по копирование свойств из первой даты и времени элемента управления в любой панели инструментов, который имеет тот же идентификатор команды, что и этот объект. Если нет панель инструментов содержит элемент управления даты и времени, который имеет тот же идентификатор команды, что и этот объект, этот метод не выполняет никаких действий.

Дополнительные сведения о **Настройка** диалоговом окне см. в разделе [класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd

Вызывается платформой при вставке кнопки в панели инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Нового родительского окна.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), повторно создав внутренний `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick

Вызывается платформой, когда пользователь щелкает элемент управления.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Не используется.

*bDelay*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки обрабатывает сообщение щелкните; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), возвращая ненулевое значение, если внутренний `CMFCToolBarDateTimeCtrlImpl` объект является видимым.

##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor

Вызывается платформой, когда родительский инструментов обрабатывает wm_ctlcolor-сообщение.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, которое отображает кнопки.

*nCtlColor*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор глобального кисть, которая инфраструктура использует для рисования фона кнопки.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), путем задания текста и фоновых цветов в контексте предоставленного устройства глобальный текст и фон, соответственно.

Дополнительные сведения о глобальных параметров, доступных для приложения, см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged

Вызывается платформой при изменении глобального шрифта.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.

Дополнительные сведения о глобальных параметров, доступных для приложения, см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove

Вызывается платформой при перемещении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновив позицию внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow

Вызывается платформой при кнопка становится видимым или невидимым.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
[in] Указывает, видима ли кнопка. Если этот параметр имеет значение TRUE, то кнопка отображается. В противном случае кнопка не видна.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопку, если *bShow* имеет значение TRUE. В противном случае этот метод скрывает кнопку.

##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize

Вызывается платформой при панели родительского изменении ее размера или положения и это изменение приводит к изменить размер кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*iSize*<br/>
[in] Новая ширина кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)), обновив размер и положение внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.

##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip

Вызывается платформой, когда родительский инструментов обновляет его текст подсказки.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Родительское окно.

*iButtonIndex*<br/>
[in] Отсчитываемый от нуля индекс кнопок в коллекции кнопок панели родительского.

*wndToolTip*<br/>
[in] Элемент управления, отображающий текст всплывающей подсказки.

*str*<br/>
[out] Объект `CString` объект, получающий обновленный подсказку.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод обновляет текст подсказки; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, связанный с кнопкой. Если кнопка не закреплено по горизонтали, этот метод не выполняет никаких действий и возвращает значение FALSE.

##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime

Задает дату и время в элементе управления.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>Параметры

*timeNew*<br/>
[in] В первой версии, ссылку на [класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий время, к которому будет задано элемента управления. Во второй версии, указатель на [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий время, к которому будет задано элемента управления.

*pTimeNew*<br/>
[in] Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую время, к которому будет задано элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Задает время в элемент управления выбора даты и времени путем вызова [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).

##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll

Задает дату и время во всех экземплярах элемента управления выбора времени, с указанным идентификатором команды.

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

*uiCmd*<br/>
[in] Указывает идентификатор команды кнопки панели инструментов.

*timeNew*<br/>
[in] В первой версии [класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий время, к которому будет задано элемента управления. Во второй версии, указатель на [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий время, к которому будет задано элемента управления.

*pTimeNew*<br/>
[in] Указатель на [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, содержащую время, к которому будет задано элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Вид для кнопки панели инструментов с помощью указанного идентификатора команды и задает время в элемент управления выбора даты и времени путем вызова [CMFCToolBarDateTimeCtrl::SetTime](#settime).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)


---
title: Класс CMFCToolBarDateTimeCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 340f9f698d63587b7a3812d5922d8963c87751ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctoolbardatetimectrl-class"></a>Класс CMFCToolBarDateTimeCtrl
Кнопка панели инструментов, содержащий элемент выбора даты и времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|Создает объект `CMFCToolBarDateTimeCtrl`.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|Указывает, может ли пользователь растянуть кнопки во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Зарезервировано для будущего использования.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Копирует текст с помощью кнопки панели инструментов в меню.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarDateTimeCtrl` объекта в приложении, который имеет указанный идентификатор команды.|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Возвращает указатель на элемент выбора даты и времени.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Возвращает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Получает выбранный период времени из элемент выбора даты и времени и помещает его в указанном [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Возвращает выбранный период времени с помощью элемента управления кнопки выбора времени, имеющий указанный идентификатор команды.|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщения. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Вызывается платформой, когда пользователь щелкает элемент управления. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Вызывается платформой при обработке родительского инструментов `WM_CTLCOLOR` сообщения. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Вызывается платформой для отрисовки кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Вызывается платформой для отрисовки кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается платформой при изменении глобальных шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Вызывается платформой при перемещении родительского инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Вызывается платформой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Вызывается платформой при инструментов родительского изменяет его размер или положение и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Вызывается платформой, когда родительский инструментов обновляет его текст всплывающей подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Считывает этот объект из архива или записывает его в архив (переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Задает стиль кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Задает дату и время в элементе управления.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Задает дату и время во всех экземплярах элементе управления с идентификатором указанную команду.|  
  
## <a name="remarks"></a>Примечания  
 Пример того, как использовать элемент выбора даты и времени см. в разделе ToolbarDateTimePicker образца проекта. Сведения о добавлении кнопок панели инструментов см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
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
 Этот метод возвращает `TRUE`.  
  
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
 [in] `uiID`  
 Идентификатор элемента управления.  
  
 [in] `iImage`  
 Индекс изображения в панели инструментов `CMFCToolBarImages` объекта.  
  
 [in] `dwStyle`  
 Стиль `CMFCToolBarDateTimeCtrlImpl` окно, которое создается, когда пользователь нажимает кнопку.  
  
 [in] `iWidth`  
 Ширина элемента управления (в пикселях).  
  
### <a name="remarks"></a>Примечания  
 Данный объект инициализирован системной даты и времени. Стиль окна внутренней `CMFCToolBarDateTimeCtrlImpl` объект включает в себя `dwStyle` параметр и `WS_CHILD` и `WS_VISIBLE` стили. Эти стили нельзя изменить с помощью `CMFCToolBarDateTimeCtrl::SetStyle`. Используйте `SetStyle` Чтобы изменить стиль `CMFCToolBarDateTimeCtrl` элемента управления.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCToolBarDateTimeCtrl` класса. Этот фрагмент кода является частью [Выбор даты и времени инструментов Образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom  
 Копирует свойства другой кнопки панели инструментов в текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» из которого выполняется копирование.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для копирования другую кнопку эта кнопка панели инструментов. `src` должен иметь тип `CMFCToolBarDateTimeCtrl`.  
  
##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 Копирует текст с помощью кнопки панели инструментов в меню.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menuButton`  
 Ссылка на целевой кнопкой меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), загрузив строкового ресурса, связанный с Идентификатором команды элемента управления. Дополнительные сведения о строковых ресурсов см. в разделе [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).  
  
##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd  
 Извлекает первый `CMFCToolBarDateTimeCtrl` объекта в приложении, который имеет указанный идентификатор команды.  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки для извлечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый `CMFCToolBarDateTimeCtrl` объекта в приложении, который имеет указанный идентификатор команды, или `NULL` Если `CMFCToolBarDateTimeCtrl` объекты имеют указанный идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод общей программы используется методами, такими как [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) и [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) указать или получить время и дату, время всех экземпляров Выбор элемента управления, имеющего указанный идентификатор команды.  
  
##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 Возвращает указатель на элемент выбора даты и времени.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на управления выбора даты и времени; или `NULL` Если элемент управления не существует.  
  
### <a name="remarks"></a>Примечания  
 `CMFCToolBarDateTimeCtrl` Класса инициализирует `m_pWndDateTime` член данных при вставке `CMFCToolBarDateTimeCtrl` объекта в панели инструментов.  
  
##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd  
 Возвращает дескриптор окна, связанный с кнопкой панели инструментов.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна, связанный с кнопкой панели инструментов даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод.  
  
##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime  
 Возвращает выбранный период времени в соответствующую дату и элементе управления и помещает его в указанном [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `[out] timeDest`  
 В первой перегрузке [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о времени системы. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о времени системы.  
  
 `[out] pTimeDest`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведения о времени системы. Значение не должно быть равно `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке ненулевое значение, если время успешно записан [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта; в противном случае — 0. В перегрузках второй и третий, возвращаемым значением является `DWORD` равен dwFlag элемент, который был задан в [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры.  
  
### <a name="remarks"></a>Примечания  
 Задает метод [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры dwFlags члена для указания того, установлен ли средство выбора даты и времени в дату и время. Если значение равно GDT_NONE, элемент управления устанавливать `no date` состояние и использует DTS_SHOWNONE стиль. Если возвращаемое значение равно GDT_VALID, системное время успешно сохранен в месте назначения.  
  
##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll  
 Возвращает время, выбранное пользователем с помощью элемента управления кнопки выбора времени, имеющий указанный идентификатор команды.  
  
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
 `[in] uiCmd`  
 Указывает идентификатор команды кнопки панели инструментов.  
  
 `[out] timeDest`  
 В первой перегрузке [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о времени системы. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о времени системы.  
  
 `[out] pTimeDest`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведения о времени системы. Значение не должно быть равно `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если платформа не удается найти кнопку панели инструментов, соответствующий идентификатор команды `uiCmd`, возвращается нуль в первой перегрузке и GDT_NONE в других перегрузок. При обнаружении кнопки панели инструментов, возвращается то же, что возвращаемое из вызова [CMFCToolBarDateTimeCtrl::GetTime](#gettime) на эту кнопку. Возвращаемое значение 0 или GDT_NONE может произойти при обнаружении кнопки, который указывает, что вызов `GetTime` не вернул допустимое Дата по другой причине.  
  
### <a name="remarks"></a>Примечания  
 Этот метод ищет кнопки панели инструментов, имеющий указанный идентификатор команды и вызовы [CMFCToolBarDateTimeCtrl::GetTime](#gettime) метод на эту кнопку.  
  
##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder  
 Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка отображается его границы, когда выбран; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает ненулевое значение, если элемент управления является видимым.  
  
##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand  
 Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщения.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iNotifyCode`  
 Сообщение уведомления, связанный с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если кнопки обрабатывает `WM_COMMAND` сообщения, или `FALSE` для указания обработки сообщения с панели инструментов родительского.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при намерении отправки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение родительского окна.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737) уведомления. Она обновляет состояние внутреннего времени и обновляет свойство времени всех `CMFCToolBarDateTimeCtrl` объекты с тем же команда идентификатор.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), путем копирования свойства из первой даты и времени элемента управления в любой панели инструментов, который имеет тот же идентификатор команды, что и данный объект. Если элемент управления даты и времени, который имеет тот же идентификатор команды, что и данный объект имеет без панелей инструментов, этот метод не выполняет никаких действий.  
  
 Дополнительные сведения о **Настройка** диалоговое окно, в разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 Вызывается платформой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Новый родительского окна.  
  
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
 [in] `pWnd`  
 Не используется.  
  
 [in] `bDelay`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопке обрабатывает сообщения нажмите кнопку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), возвращая ненулевое значение, если внутренний `CMFCToolBarDateTimeCtrlImpl` объект является видимым.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor  
 Вызывается платформой при обработке родительского инструментов `WM_CTLCOLOR` сообщения.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства, который отображает кнопки.  
  
 [in] `nCtlColor`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор глобального кисть, платформа использует в качестве фона кнопки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), путем задания текста и фоновый цвет контекста устройства, предоставленный для глобального текст и цвет фона, соответственно.  
  
 Дополнительные сведения о глобальных параметрах, доступных для приложения см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 Вызывается платформой при изменении глобальных шрифта.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.  
  
 Дополнительные сведения о глобальных параметрах, доступных для приложения см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove  
 Вызывается платформой при перемещении родительского инструментов.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) путем обновления позиция внутренней `CMFCToolBarDateTimeCtrlImpl` объекта.  
  
##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow  
 Вызывается платформой при кнопка становится видимым или невидимым.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, отображается ли кнопка. Если этот параметр равен `TRUE`, то кнопка отображается. В противном случае кнопка не отображается.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопки, если `bShow` — `TRUE`. В противном случае этот метод скрывает кнопку.  
  
##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize  
 Вызывается платформой при инструментов родительского изменяет его размер или положение и это изменение приводит к изменить размер кнопки.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iSize`  
 Новая ширина кнопки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) путем обновления размер и положение внутренней `CMFCToolBarDateTimeCtrlImpl` объекта.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 Вызывается платформой, когда родительский инструментов обновляет его текст всплывающей подсказки.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Родительское окно.  
  
 [in] `iButtonIndex`  
 Отсчитываемый от нуля индекс кнопки в родительской коллекции кнопки.  
  
 [in] `wndToolTip`  
 Элемент управления, отображающий текст всплывающей подсказки.  
  
 [выходной] `str`  
 Объект `CString` объект, получающий обновленный подсказка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод обновляет текст всплывающей подсказки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст всплывающей подсказки, связанный с кнопкой. Если кнопка не закреплена горизонтально, этот метод не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime  
 Задает дату и время в элементе управления.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] timeNew`  
 В первой версии ссылку на [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий время, к которому будет установить элемент управления. Во второй версии указатель [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, который содержит время, к которому будет установить элемент управления.  
  
 `[in] pTimeNew`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую время, к которому будет установить элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Задает время в элемент выбора даты и времени путем вызова [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).  
  
##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll  
 Задает дату и время во всех экземплярах элементе управления с идентификатором указанную команду.  
  
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
 `[in] uiCmd`  
 Указывает идентификатор команды кнопки панели инструментов.  
  
 `[in] timeNew`  
 В первой версии [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий время, к которому будет установить элемент управления. Во второй версии указатель [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, который содержит время, к которому будет установить элемент управления.  
  
 `[in] pTimeNew`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую время, к которому будет установить элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Ищет указанный идентификатор команды кнопки на панели управления и задает время в элемент выбора даты и времени путем вызова [CMFCToolBarDateTimeCtrl::SetTime](#settime).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)




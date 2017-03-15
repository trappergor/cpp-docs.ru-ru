---
title: "Класс CMFCToolBarDateTimeCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OnDrawOnCustomizeList
- CMFCToolBarDateTimeCtrl::OnDraw
- OnDraw
- CMFCToolBarDateTimeCtrl.Serialize
- CMFCToolBarDateTimeCtrl.OnSize
- CMFCToolBarDateTimeCtrl.OnDrawOnCustomizeList
- OnSize
- OnCalculateSize
- CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl::OnCalculateSize
- SetStyle
- CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList
- CMFCToolBarDateTimeCtrl.OnDraw
- CMFCToolBarDateTimeCtrl.SetStyle
- CMFCToolBarDateTimeCtrl::SetStyle
- CMFCToolBarDateTimeCtrl.OnCalculateSize
- CMFCToolBarDateTimeCtrl::Serialize
- CMFCToolBarDateTimeCtrl::OnSize
- Serialize
dev_langs:
- C++
helpviewer_keywords:
- SetStyle method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- CMFCToolBarDateTimeCtrl class
- Serialize method
- OnSize method
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9558d62710c7be571d6aefab2c44fe504ca56d60
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbardatetimectrl-class"></a>Класс CMFCToolBarDateTimeCtrl
Кнопка панели инструментов, который содержит элемент выбора даты и времени.  
  
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
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|Копирует свойства кнопки панели инструментов, для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|Зарезервировано для будущего использования.|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|Копирует текст из кнопки панели инструментов меню.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении, которое имеет идентификатор указанной команды.|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|Возвращает указатель на элемент управления выбора даты и времени.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|Получает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|Возвращает время, выбранный из элемента управления выбора даты и времени и помещает его в указанном [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|Возвращает время, выбранного с помощью кнопки управления выбора времени, имеет идентификатор указанной команды.|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается инфраструктурой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|Вызывается инфраструктурой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|Вызывается платформой, когда пользователь щелкает элемент управления. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|Вызывается инфраструктурой при обработке родительского инструментов `WM_CTLCOLOR` сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|Вызывается платформой для отображения кнопки с помощью указанного стили и параметры. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|Вызывается платформой для отображения кнопки в **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается инфраструктурой при изменении глобальных шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|Вызывается инфраструктурой при перемещении родительского инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|Вызывается инфраструктурой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|Вызывается инфраструктурой при инструментов родительской изменении ее размера или положения и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|Вызывается средой во время обновления инструментов родительской его текст всплывающей подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|Считывает этот объект из архива и записывает его в архив (переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|Задает стиль кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|Задает дату и время в элементе управления.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|Задает дату и время в всем экземплярам элемента управления для выбора времени, указанному идентификатору команды.|  
  
## <a name="remarks"></a>Примечания  
 Пример использования элемента управления выбора даты и времени см. Образец ToolbarDateTimePicker проекта. Сведения о добавлении кнопок панели инструментов в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbardatetimectrl.h  
  
##  <a name="a-namecanbestretcheda--cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched  
 Указывает, может ли пользователь растянуть кнопки во время настройки.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не разрешается растянуть кнопки панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопки даты и времени во время настройки.  
  
##  <a name="a-namecmfctoolbardatetimectrla--cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
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
 Этот объект инициализируется системной даты и времени. Внутренний стиль окна `CMFCToolBarDateTimeCtrlImpl` объект включает в себя `dwStyle` параметр и `WS_CHILD` и `WS_VISIBLE` стили. Не удается изменить эти стили с помощью `CMFCToolBarDateTimeCtrl::SetStyle`. Используйте `SetStyle` Чтобы изменить стиль `CMFCToolBarDateTimeCtrl` элемента управления.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCToolBarDateTimeCtrl` класса. Этот фрагмент кода является частью [образец инструментов Выбор даты и времени](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="a-namecopyfroma--cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::CopyFrom  
 Копирует свойства кнопки панели инструментов, для текущей кнопки.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка «источник» для копирования.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для копирования другой кнопки панели инструментов эта кнопка панели инструментов. `src`должен быть типа `CMFCToolBarDateTimeCtrl`.  
  
##  <a name="a-nameexporttomenubuttona--cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 Копирует текст из кнопки панели инструментов меню.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menuButton`  
 Ссылка на кнопке меню целевой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), загрузив строковый ресурс, связанный с Идентификатором команды элемента управления. Дополнительные сведения о строковых ресурсов см. в разделе [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring).  
  
##  <a name="a-namegetbycmda--cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>CMFCToolBarDateTimeCtrl::GetByCmd  
 Извлекает первый `CMFCToolBarDateTimeCtrl` объект в приложении, которое имеет идентификатор указанной команды.  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды кнопки для извлечения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый `CMFCToolBarDateTimeCtrl` объект в приложении, которое содержит заданный идентификатор команды, или `NULL` Если `CMFCToolBarDateTimeCtrl` объекты имеют идентификатор указанной команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служебной программы используется методы, такие как [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) и [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) задать или получить время и дату всем экземплярам элемента управления для выбора времени, указанному идентификатору команды.  
  
##  <a name="a-namegetdatetimectrla--cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 Возвращает указатель на элемент управления выбора даты и времени.  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на управления выбора даты и времени; или `NULL` Если элемент управления не существует.  
  
### <a name="remarks"></a>Примечания  
 `CMFCToolBarDateTimeCtrl` Класса инициализирует `m_pWndDateTime` член данных при вставке `CMFCToolBarDateTimeCtrl` объекта в панели инструментов.  
  
##  <a name="a-namegethwnda--cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd  
 Получает дескриптор окна, связанный с кнопкой панели инструментов.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор окна, связанный с кнопкой панели инструментов даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метод.  
  
##  <a name="a-namegettimea--cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime  
 Возвращает указанное время из связанных даты и элементе управления и помещает его в указанном [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `[out] timeDest`  
 В первой перегрузке [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о системе времени. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о системе времени.  
  
 `[out] pTimeDest`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведений о системе времени. Значение не должно быть равно `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой перегрузке ненулевое значение, если время успешно записан [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта; в противном случае — 0. На второй и третьей перегрузки, возвращаемым значением является `DWORD` равен dwFlag элемент, который был задан в [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры.  
  
### <a name="remarks"></a>Примечания  
 Задает метод [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры dwFlags члена для указания того, установлен ли элемент выбора даты и времени, даты и времени. Если значение равно GDT_NONE, элемент управления имеет значение `no date` состояние и использует стиль DTS_SHOWNONE. Если возвращаемое значение равно GDT_VALID, системное время успешно сохранен в месте назначения.  
  
##  <a name="a-namegettimealla--cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll  
 Возвращает время, выбранное пользователем с помощью кнопки управления выбора времени, имеет идентификатор указанной команды.  
  
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
 В первой перегрузке [COleDateTime класс](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о системе времени. Во второй перегрузке [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о системе времени.  
  
 `[out] pTimeDest`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведений о системе времени. Значение не должно быть равно `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если платформа не удается найти кнопку панели инструментов, соответствующий идентификатор команды `uiCmd`, возвращаемое значение равно нулю, в первой перегрузке и GDT_NONE в другие перегрузки. При обнаружении кнопки панели инструментов, возвращается таким же, как возвращаемое значение вызова [CMFCToolBarDateTimeCtrl::GetTime](#gettime) этой кнопки. Возвращаемое значение&0; или GDT_NONE может произойти при обнаружении кнопки, который указывает, что вызов `GetTime` не вернул допустимое по другой причине.  
  
### <a name="remarks"></a>Примечания  
 Этот метод ищет кнопку панели инструментов с заданным Идентификатором команды и вызывает метод [CMFCToolBarDateTimeCtrl::GetTime](#gettime) метод этой кнопки.  
  
##  <a name="a-namehavehotbordera--cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder  
 Определяет, отображается ли границы кнопки, когда пользователь выбирает кнопку.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если кнопка отображается его границы, если установлен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает ненулевое значение, если элемент управления является видимым.  
  
##  <a name="a-namenotifycommanda--cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarDateTimeCtrl::NotifyCommand  
 Указывает, обрабатывает ли кнопки [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iNotifyCode`  
 Сообщение уведомления, связанный с командой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если кнопка обрабатывает `WM_COMMAND` сообщения, или `FALSE` для указания, что сообщение должно быть обработано родительским инструментов.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда он собирается отправить [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) сообщение родительского окна.  
  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737) уведомления. Он обновляет состояние внутреннее время и обновляет свойство времени всех `CMFCToolBarDateTimeCtrl` команды объектов с тем же идентификатором.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 Вызывается инфраструктурой при добавлении кнопки **Настройка** диалоговое окно.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage), путем копирования свойств из первой даты и время управления в любой панели инструментов, который имеет тот же идентификатор команды, что и данный объект. Если нет панели инструментов управления даты и времени, который имеет тот же идентификатор команды, что и данный объект, этот метод не выполняет никаких действий.  
  
 Дополнительные сведения о **Настройка** диалоговом разделе [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 Вызывается инфраструктурой при вставке кнопки в панели инструментов.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndParent`  
 Новый родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), повторно создав внутренний `CMFCToolBarDateTimeCtrlImpl` объекта.  
  
##  <a name="a-nameonclicka--cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick  
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
 Ненулевое значение, если кнопка обрабатывает сообщение щелкните; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), возвращая ненулевое значение, если внутренний `CMFCToolBarDateTimeCtrlImpl` объект является видимым.  
  
##  <a name="a-nameonctlcolora--cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl::OnCtlColor  
 Вызывается инфраструктурой при обработке родительского инструментов `WM_CTLCOLOR` сообщение.  
  
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
 Дескриптор для глобального кисть, она используется для рисования фона кнопки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию базового класса, [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor), установив текста и фоновых цветов контекста устройства, предоставленный глобальный текста и фона, соответственно.  
  
 Дополнительные сведения о глобальных параметров, доступных для вашего приложения, в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 Вызывается инфраструктурой при изменении глобальных шрифта.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.  
  
 Дополнительные сведения о глобальных параметров, доступных для вашего приложения, в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonmovea--cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove  
 Вызывается инфраструктурой при перемещении родительского инструментов.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновив положение внутренний `CMFCToolBarDateTimeCtrlImpl` объекта.  
  
##  <a name="a-nameonshowa--cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>CMFCToolBarDateTimeCtrl::OnShow  
 Вызывается инфраструктурой при кнопка становится видимым или невидимым.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, видима ли кнопка. Если этот параметр равен `TRUE`, то кнопка отображается. В противном случае — кнопка не отображается.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопку, если `bShow` — `TRUE`. В противном случае этот метод скрывает кнопку.  
  
##  <a name="a-nameonsizea--cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>CMFCToolBarDateTimeCtrl::OnSize  
 Вызывается инфраструктурой при инструментов родительской изменении ее размера или положения и это изменение приводит к изменить размер кнопки.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iSize`  
 Новая ширина кнопки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)), обновив размер и положение внутреннего `CMFCToolBarDateTimeCtrlImpl` объекта.  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 Вызывается средой во время обновления инструментов родительской его текст всплывающей подсказки.  
  
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
 Объект `CString` объект, который получает обновленный подсказку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод обновляет текст всплывающей подсказки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст всплывающей подсказки, связанный с кнопкой. Если кнопка не закреплена горизонтально, этот метод не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="a-namesettimea--cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>CMFCToolBarDateTimeCtrl::SetTime  
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
 Задает время в элемент управления выбора даты и времени путем вызова [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime).  
  
##  <a name="a-namesettimealla--cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll  
 Задает дату и время в всем экземплярам элемента управления для выбора времени, указанному идентификатору команды.  
  
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
 Ищет заданный идентификатор команды кнопки на панели управления и задает время в элементе управления выбора даты и времени путем вызова [CMFCToolBarDateTimeCtrl::SetTime](#settime).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Пошаговое руководство: Добавление элементов управления в панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)





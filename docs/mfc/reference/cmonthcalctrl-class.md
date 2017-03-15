---
title: "CMonthCalCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonthCalCtrl
dev_langs:
- C++
helpviewer_keywords:
- month calendar controls, CMonthCalCtrl class
- common controls, Internet Explorer 4.0
- CMonthCalCtrl class
- Internet Explorer 4.0 common controls
- month calendar controls
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
caps.latest.revision: 23
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
ms.openlocfilehash: 96cefbeb7692a07088f596fe08fec2bf179b98bc
ms.lasthandoff: 02/24/2017

---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl-класс
Инкапсулирует функциональность элемента управления "календарь месяца".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Создает объект `CMonthCalCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](#create)|Создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.|  
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Получает ширину границы элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Получает число календарей, отображаемый в элементе управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Получает сведения об элементе управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetCalID](#getcalid)|Извлекает идентификатор календаря для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetColor](#getcolor)|Возвращает цвет заданную область элемента управления календаря на месяц.|  
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Извлекает представления, отображаемого элементом управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetCurSel](#getcursel)|Получает системное время, обозначенный выбранной даты.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Возвращает первый день недели, отображаемый в левом столбце календаря.|  
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Получает текущее максимальное количество дней, которые могут быть выбраны в элементе управления calendar month.|  
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Получает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Получает минимальный размер, требуемый для отображения полного месяца в элементе управления calendar month.|  
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Возвращает скорость прокрутки для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Получает дату сведения, представляющие верхние и нижние пределы отображения элемента управления календарем месяца.|  
|[CMonthCalCtrl::GetRange](#getrange)|Получает текущие даты минимальное и максимальное значение в элементе управления calendar month.|  
|[CMonthCalCtrl::GetSelRange](#getselrange)|Извлекает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного пользователем.|  
|[CMonthCalCtrl::GetToday](#gettoday)|Извлекает сведения о датах по дате, указанной как «сегодня» для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::HitTest](#hittest)|Определяет, какие части элемента управления календарем месяца в определенный момент на экране.|  
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление века.|  
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десятилетия.|  
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.|  
|[CMonthCalCtrl::IsYearView](#isyearview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.|  
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Задает ширину границы элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Задает ширину границы элемента управления calendar текущего месяца по умолчанию.|  
|[CMonthCalCtrl::SetCalID](#setcalid)|Задает идентификатор календаря для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Задает элемент управления calendar текущего месяца к представлению века.|  
|[CMonthCalCtrl::SetColor](#setcolor)|Задает цвет для заданной области элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Задает элемент управления calendar текущего месяца для отображения в указанном представлении.|  
|[CMonthCalCtrl::SetCurSel](#setcursel)|Задает текущей выбранной даты для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetDayState](#setdaystate)|Задает отображение дней в элементе управления calendar month.|  
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Задает текущий месяц календаря элемента управления представления десятилетия.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Задает день недели, отображаемый в левом столбце календаря.|  
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Задает максимальное количество дней, которые могут быть выбраны в элементе управления calendar month.|  
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Задает скорость прокрутки для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Задает элемент управления calendar текущего месяца для отображения представления месяца.|  
|[CMonthCalCtrl::SetRange](#setrange)|Задает минимальное и максимальное допустимые даты для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetSelRange](#setselrange)|Задает Выбор календарь на месяц элемента управления для указанного диапазона дат.|  
|[CMonthCalCtrl::SetToday](#settoday)|Задает элемент управления calendar за текущий день.|  
|[CMonthCalCtrl::SetYearView](#setyearview)|Задает текущий месяц календаря элемента управления представления года.|  
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Перерисовывает месячный календарь управление его размер, минимум, один месяц.|  
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, содержащий все календари, которые помещаются в заданном прямоугольнике.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления calendar month предоставляет пользователю интерфейс простого календарь, из которого пользователь может выбрать дату. Пользователь может изменить отображение по:  
  
-   Прокрутка назад и вперед от месяца к месяцу.  
  
-   Щелкнув сегодня текст, отображаемый в текущий день (если **MCS_NOTODAY** стиля не используется).  
  
-   Комплектации, месяц или год всплывающего меню.  
  
 Можно настроить месяц календаря, применяя различные стили к объекту при создании элемента управления. Эти стили, описаны в [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Элемент управления Календарь на месяц могут отображать более чем одного месяца, и она может указать специальные дни (например, праздники), полужирный даты.  
  
 Дополнительные сведения об использовании элемента управления calendar месяца в разделе [CMonthCalCtrl с помощью](../../mfc/using-cmonthcalctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdtctl.h  
  
##  <a name="a-namecmonthcalctrla--cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>CMonthCalCtrl::CMonthCalCtrl  
 Создает объект `CMonthCalCtrl`.  
  
```  
CMonthCalCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать **создать** после создания объекта.  
  
##  <a name="a-namecreatea--cmonthcalctrlcreate"></a><a name="create"></a>CMonthCalCtrl::Create  
 Создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);

 
virtual BOOL Create(
    DWORD dwStyle,  
    const POINT& pt,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стили Windows применяется к элементу управления календарного месяца. В разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о стилях.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. Содержит положение и размер элемента управления calendar month.  
  
 `pt`  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, определяющий расположение элемента управления calendar month.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления calendar month. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления calendar month элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создание месяц календаря управления в два этапа:  
  
1.  Вызов [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) для создания `CMonthCalCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает элемент управления calendar month и присоединяет его к `CMonthCalCtrl` объекта.  
  
 При вызове **создать**, общие элементы управления инициализируются. Версия **создать** вы вызова определяет способ изменения размеров:  
  
-   Чтобы MFC автоматическое изменение размера элемента управления на один месяц, вызывать переопределенный метод, использующий `pt` параметр.  
  
-   Для изменения размера элемента управления самостоятельно, вызывает переопределение функции, использует `rect` параметр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#1;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]  
  
##  <a name="a-namegetcalendarbordera--cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>CMonthCalCtrl::GetCalendarBorder  
 Получает ширину границы элемента управления calendar текущего месяца.  
  
```  
int GetCalendarBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина границы элемента управления, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760945) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcalendarcounta--cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>CMonthCalCtrl::GetCalendarCount  
 Получает число календарей, отображаемый в элементе управления calendar текущего месяца.  
  
```  
int GetCalendarCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество календарей, отображаемый в текущий момент в элементе управления calendar month. Максимальное число календарей равно 12.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760947) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcalendargridinfoa--cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>CMonthCalCtrl::GetCalendarGridInfo  
 Получает сведения об элементе управления calendar текущего месяца.  
  
```  
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pmcGridInfo`|Указатель на [MCGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760925) структуру, которая получает сведения об элементе управления calendar текущего месяца. Вызывающий объект отвечает за выделение и инициализации этой структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760949) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода `GetCalendarGridInfo` метод для извлечения календарную дату, который отображает элемент управления calendar текущего месяца.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]  
  
##  <a name="a-namegetcalida--cmonthcalctrlgetcalid"></a><a name="getcalid"></a>CMonthCalCtrl::GetCalID  
 Извлекает идентификатор календаря для элемента управления calendar текущего месяца.  
  
```  
CALID GetCalID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из [календаря идентификатор](http://msdn.microsoft.com/library/windows/desktop/dd317732) константы.  
  
### <a name="remarks"></a>Примечания  
 Обозначает идентификатор календарь календарь региона, например григорианский (локализованный), японский или хиджра календари. Приложение может использовать идентификатор календаря, который имеет поддержка функции различных языков.  
  
 Этот метод отправляет [MCM_GETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760951) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcolora--cmonthcalctrlgetcolor"></a><a name="getcolor"></a>CMonthCalCtrl::GetColor  
 Получает цвет области месяца календаря управления, указанный в `nRegion`.  
  
```  
COLORREF GetColor(int nRegion) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nRegion`  
 Область элемента управления calendar month, из которого извлекается цвет. Список значений см. в разделе `nRegion` параметр [SetColor](#setcolor).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, указывающее цвет, связанный с частью элемента управления calendar month, в случае успешного выполнения. В противном случае — эта функция-член возвращает значение -1.  
  
##  <a name="a-namegetcurrentviewa--cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>CMonthCalCtrl::GetCurrentView  
 Извлекает представления, отображаемого элементом управления calendar текущего месяца.  
  
```  
DWORD GetCurrentView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее представление, которое указывается одним из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`MCMV_MONTH`|Месячное представление|  
|`MCMV_YEAR`|Ежегодное представление|  
|`MCMV_DECADE`|Последнее десятилетие представления|  
|`MCMV_CENTURY`|Представление веке|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 Следующие отчеты пример кода, которые просмотреть календарь месяца, в настоящее время управлять отображением.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]  
  
##  <a name="a-namegetcursela--cmonthcalctrlgetcursel"></a><a name="getcursel"></a>CMonthCalCtrl::GetCurSel  
 Получает системное время, обозначенный выбранной даты.  
  
```  
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;  
   
BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `refDateTime`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта. Получает текущее время.  
  
 `pDateTime`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет получать сведения о выбранной дате. Этот параметр должен быть допустимым адресом и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; otherwize 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb760957), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Эта функция-член не выполняется, если стиль **MCS_MULTISELECT** имеет значение.  
  
 В реализации MFC `GetCurSel`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
##  <a name="a-namegetfirstdayofweeka--cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>CMonthCalCtrl::GetFirstDayOfWeek  
 Возвращает первый день недели, отображаемый в левом столбце календаря.  
  
```  
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pbLocal*  
 Указатель на **BOOL** значение. Если значение равно нулю, значение элемента управления не соответствует параметр на панели управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее первый день недели. В разделе **примечания** Дополнительные сведения о представляют эти целых чисел.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb760958), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Дни недели, представляются в виде целых чисел, следующим образом.  
  
|Значение|День недели|  
|-----------|---------------------|  
|0|Понедельник|  
|1|Вторник|  
|2|Среда|  
|3|Четверг|  
|4|Пятница|  
|5|Суббота|  
|6|Воскресенье|  
  
### <a name="example"></a>Пример  
  В примере показано [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).  
  
##  <a name="a-namegetmaxselcounta--cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>CMonthCalCtrl::GetMaxSelCount  
 Получает текущее максимальное количество дней, которые могут быть выбраны в элементе управления calendar month.  
  
```  
int GetMaxSelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее общее количество дней, которые могут быть выбраны для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760960), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Используйте эту функцию-член для элементов управления с **MCS_MULTISELECT** набор стилей.  
  
### <a name="example"></a>Пример  
  В примере показано [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).  
  
##  <a name="a-namegetmaxtodaywidtha--cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>CMonthCalCtrl::GetMaxTodayWidth  
 Получает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.  
  
```  
DWORD GetMaxTodayWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина «Сегодня» строки в пикселях.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetMaxTodayWidth` метод.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Пользователя можно вернуться на текущую дату, щелкнув строку «Сегодня», который отображается в нижней части элемента управления Календарь месяца. Строка «Сегодня» содержит текст даты и метки.  
  
 Этот метод отправляет [MCM_GETMAXTODAYWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760962) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetminreqrecta--cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>CMonthCalCtrl::GetMinReqRect  
 Получает минимальный размер, требуемый для отображения полного месяца в элементе управления calendar month.  
  
```  
BOOL GetMinReqRect(RECT* pRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pRect`  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, получит сведения ограничивающего прямоугольника. Этот параметр должен быть допустимым адресом и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном завершении, эта функция-член возвращает ненулевое значение, и `lpRect` Получает ограничивающий данные. Если операция завершилась неудачей, функция-член возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMINREQRECT](http://msdn.microsoft.com/library/windows/desktop/bb760978), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmonthdeltaa--cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>CMonthCalCtrl::GetMonthDelta  
 Возвращает скорость прокрутки для элемента управления календаря на месяц.  
  
```  
int GetMonthDelta() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Скорость прокрутки для элемента управления calendar month. Скорость прокрутки — количество месяцев, что элемент управления перемещается отображения, когда пользователь нажимает кнопку прокрутки один раз.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb760980), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmonthrangea--cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>CMonthCalCtrl::GetMonthRange  
 Получает дату сведения, представляющие верхние и нижние пределы отображения элемента управления календарем месяца.  
  
```  
int GetMonthRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    CTime& refMinRange,  
    CTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `refMinRange`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальной даты, допустимой.  
  
 `refMaxRange`  
 Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.  
  
 `pMinRange`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце нижнего диапазона.  
  
 `pMaxRange`  
 Указатель на `SYSTEMTIME` структура, содержащая дату в конце наибольший диапазон.  
  
 `dwFlags`  
 Значение, указывающее область границы диапазона, который требуется получить. Это значение должно быть одним из следующих.  
  
|Значение|Значение|  
|-----------|-------------|  
|GMR_DAYSTATE|Включить начальные и завершающие месяцев видимого диапазона, которые отображаются только частично.|  
|GMR_VISIBLE|Включать только эти месяцы, полностью отображаемых.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Integer, представляющее диапазона, в месяцах, занимаемых двух ограничений обозначается `refMinRange` и `refMaxRange` в первой и второй версии, или `pMinRange` и `pMaxRange` в третьей версии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMONTHRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760981), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `GetMonthRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
  В примере показано [CMonthCalCtrl::SetDayState](#setdaystate).  
  
##  <a name="a-namegetrangea--cmonthcalctrlgetrange"></a><a name="getrange"></a>CMonthCalCtrl::GetRange  
 Получает текущие даты минимальное и максимальное значение в элементе управления calendar month.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
  
DWORD GetRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pMinRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце нижнего диапазона.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , может быть равен нулю (устанавливаются без ограничений) или сочетанием следующих значений, содержащих информацию ограничение.  
  
|Значение|Значение|  
|-----------|-------------|  
|GDTR_MAX|Максимальное ограничение установлено для элемента управления; `pMaxRange` является допустимым и содержит сведения, применимые даты.|  
|GDTR_MIN|Минимальный предел задается для элемента управления; `pMinRange` является допустимым и содержит сведения, применимые даты.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760983), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `GetRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#2;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]  
  
##  <a name="a-namegetselrangea--cmonthcalctrlgetselrange"></a><a name="getselrange"></a>CMonthCalCtrl::GetSelRange  
 Извлекает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного пользователем.  
  
```  
BOOL GetSelRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange) const;  
  
BOOL GetSelRange(
    CTime& refMinRange,  
    CTime& refMaxRange) const;  
  
BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `refMinRange`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальной даты, допустимой.  
  
 `refMaxRange`  
 Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.  
  
 `pMinRange`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце нижнего диапазона.  
  
 `pMaxRange`  
 Указатель на `SYSTEMTIME` структура, содержащая дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760985), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `GetSelRange`завершится ошибкой, если применить к элементу управления календарного месяца, не использующих **MCS_MULTISELECT** стиль.  
  
 В реализации MFC `GetSelRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
##  <a name="a-namegettodaya--cmonthcalctrlgettoday"></a><a name="gettoday"></a>CMonthCalCtrl::GetToday  
 Извлекает сведения о датах по дате, указанной как «сегодня» для элемента управления календаря на месяц.  
  
```  
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;  
   
BOOL GetToday(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `refDateTime`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , показывающий текущий день.  
  
 `pDateTime`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет получать сведения о дате. Этот параметр должен быть допустимым адресом и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb760987), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `GetToday`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#3;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]  
  
##  <a name="a-namehittesta--cmonthcalctrlhittest"></a><a name="hittest"></a>CMonthCalCtrl::HitTest  
 Определяет какой управляющий элемент календаря, если он имеется в указанной позиции.  
  
```  
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```  
  
### <a name="parameters"></a>Параметры  
 *pMCHitTest*  
 Указатель на [MCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760927) структуру, содержащую попадания точек для элемента управления calendar month.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `DWORD`. Равно **uHit** членом **MCHITTESTINFO** структуры.  
  
### <a name="remarks"></a>Примечания  
 `HitTest`использует **MCHITTESTINFO** структура, которая содержит сведения о проверки нажатия.  
  
##  <a name="a-nameiscenturyviewa--cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>CMonthCalCtrl::IsCenturyView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление века.  
  
```  
BOOL IsCenturyView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если текущим представлением является представления века. в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если, сообщение возвращает `MCMV_CENTURY`, этот метод возвращает `true`.  
  
##  <a name="a-nameisdecadeviewa--cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>CMonthCalCtrl::IsDecadeView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десятилетия.  
  
```  
BOOL IsDecadeView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если текущим представлением является представления десятилетия. в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если, сообщение возвращает `MCMV_DECADE`, этот метод возвращает `true`.  
  
##  <a name="a-nameismonthviewa--cmonthcalctrlismonthview"></a><a name="ismonthview"></a>CMonthCalCtrl::IsMonthView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.  
  
```  
BOOL IsMonthView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если текущим представлением является месяц; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если, сообщение возвращает `MCMV_MONTH`, этот метод возвращает `true`.  
  
##  <a name="a-nameisyearviewa--cmonthcalctrlisyearview"></a><a name="isyearview"></a>CMonthCalCtrl::IsYearView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.  
  
```  
BOOL IsYearView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если текущим представлением является представление года; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если, сообщение возвращает `MCMV_YEAR`, этот метод возвращает `true`.  
  
##  <a name="a-namesetcalendarbordera--cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>CMonthCalCtrl::SetCalendarBorder  
 Задает ширину границы элемента управления calendar текущего месяца.  
  
```  
void SetCalendarBorder(int cxyBorder);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `cxyBorder`|Ширина границы в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Если этот метод завершается успешно, устанавливается ширина границы `cxyBorder` параметр. В противном случае — значение по умолчанию, который указан в текущем сбрасывается ширину границы [темы](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), или нуль, если не используются темы.  
  
 Этот метод отправляет [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается ширину границы месячный календарь управления до восьми пикселей. Используйте [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) метод, чтобы определить, является ли этот метод успешно выполнен.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]  
  
##  <a name="a-namesetcalendarborderdefaulta--cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>CMonthCalCtrl::SetCalendarBorderDefault  
 Задает ширину границы элемента управления calendar текущего месяца по умолчанию.  
  
```  
void SetCalendarBorderDefault();
```  
  
### <a name="remarks"></a>Примечания  
 Ширина границы задано значение по умолчанию, указанное в текущем [темы](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), или нуль, если не используются темы.  
  
 Этот метод отправляет [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcalida--cmonthcalctrlsetcalid"></a><a name="setcalid"></a>CMonthCalCtrl::SetCalID  
 Задает идентификатор календаря для элемента управления calendar текущего месяца.  
  
```  
BOOL SetCalID(CALID calid);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `calid`|Один из [календаря идентификатор](http://msdn.microsoft.com/library/windows/desktop/dd317732) константы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Указывает идентификатор календарь календарь региона, например григорианский (локализованный), японский или хиджра календари. Используйте `SetCalID` метод для отображения календаря, который задается параметром `calid` параметр, если на компьютере установлен языковой стандарт с календарем.  
  
 Этот метод отправляет [MCM_SETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760995) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода элемент управления Календарь на месяц для отображения календаря японских императоров. `SetCalID` Метод завершается успешно, только если на компьютере установлена этого календаря.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]  
  
##  <a name="a-namesetcenturyviewa--cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>CMonthCalCtrl::SetCenturyView  
 Задает элемент управления calendar текущего месяца к представлению века.  
  
```  
BOOL SetCenturyView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод установить представление `MCMV_CENTURY`, представляющий представление века.  
  
##  <a name="a-namesetcolora--cmonthcalctrlsetcolor"></a><a name="setcolor"></a>CMonthCalCtrl::SetColor  
 Задает цвет для заданной области элемента управления календаря на месяц.  
  
```  
COLORREF SetColor(
    int nRegion,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 `nRegion`  
 Целочисленное значение, задающее цвет календаря месяца для задания. Это значение может быть одно из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|MCSC_BACKGROUND|Фоновый цвет, отображаемый между месяцев.|  
|MCSC_MONTHBK|Фоновый цвет, отображаемый в области месяца.|  
|MCSC_TEXT|Цвет для отображения текста в области месяца.|  
|MCSC_TITLEBK|Фоновый цвет заглавия календаря.|  
|MCSC_TITLETEXT|Цвет для отображения текста в заглавии календаря.|  
|MCSC_TRAILINGTEXT|Цвет, используемый для отображения текста заголовка и в конце дня. Завершающие и начальные дни-это дни предыдущего и последующего месяцев, которые отображаются на текущем календаре.|  
  
 `ref`  
 Объект **COLORREF** значение для параметра цвет указанную часть элемента управления calendar month.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее указанную часть элемента управления calendar month, предыдущее значение цвета в случае успешного выполнения. В противном случае оно возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760997), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#4;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]  
  
##  <a name="a-namesetcurrentviewa--cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>CMonthCalCtrl::SetCurrentView  
 Задает элемент управления calendar текущего месяца для отображения в указанном представлении.  
  
```  
BOOL SetCurrentView(DWORD dwNewView);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwNewView`|Одно из следующих значений, определяющих ежемесячно, годовой, десяти лет или просмотр века.<br /><br /> MCMV_MONTH: Представление месячного<br /><br /> MCMV_YEAR: Ежегодное представление<br /><br /> MCMV_DECADE: Представление десятилетия<br /><br /> MCMV_CENTURY: Представление века|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_SETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760998) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcursela--cmonthcalctrlsetcursel"></a><a name="setcursel"></a>CMonthCalCtrl::SetCurSel  
 Задает текущей выбранной даты для элемента управления календаря на месяц.  
  
```  
BOOL SetCurSel(const COleDateTime& refDateTime);  
BOOL SetCurSel(const CTime& refDateTime);  
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Параметры  
 `refDateTime`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , показывающий выбранной управляющий элемент календаря.  
  
 `pDateTime`  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в качестве текущего выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb761002), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `SetCurSel`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#5;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]  
  
##  <a name="a-namesetdaystatea--cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>CMonthCalCtrl::SetDayState  
 Задает отображение дней в элементе управления calendar month.  
  
```  
BOOL SetDayState(
    int nMonths,  
    LPMONTHDAYSTATE pStates);
```  
  
### <a name="parameters"></a>Параметры  
 *nMonths*  
 Значение, указывающее, сколько элементов в массиве, `pStates` указывает.  
  
 `pStates`  
 Указатель на [MONTHDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760915) массив значений, которые определяют, как нарисовать элемент управления calendar month каждый день в его отображения. **MONTHDAYSTATE** тип данных представляет собой битовое поле, где каждый бит (от 1 до 31) представляет состояние день в месяце. Если бит включен, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться с без выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761004), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl №&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]  
  
##  <a name="a-namesetdecadeviewa--cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>CMonthCalCtrl::SetDecadeView  
 Задает текущий месяц календаря элемента управления представления десятилетия.  
  
```  
BOOL SetDecadeView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод установить представление `MCMV_DECADE`, представляет представление десятилетия.  
  
##  <a name="a-namesetfirstdayofweeka--cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>CMonthCalCtrl::SetFirstDayOfWeek  
 Задает день недели, отображаемый в левом столбце календаря.  
  
```  
BOOL SetFirstDayOfWeek(
    int iDay,  
    int* lpnOld = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *iDay*  
 Целое число, представляющее день — присвоить в качестве первого дня недели. Это значение должно быть одним из номеров день. В разделе [GetFirstDayOfWeek](#getfirstdayofweek) описание номера дня.  
  
 *lpnOld*  
 Установите указатель на целое число, указывающее первый день недели, ранее.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если предыдущий первый день недели присвоено значение, отличное от, **LOCALE_IFIRSTDAYOFWEEK**, передаваемый в день, указанный в параметре панели управления. В противном случае эта функция возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb761006), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#7;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]  
  
##  <a name="a-namesetmaxselcounta--cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>CMonthCalCtrl::SetMaxSelCount  
 Задает максимальное количество дней, которые могут быть выбраны в элементе управления calendar month.  
  
```  
BOOL SetMaxSelCount(int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 `nMax`  
 Значение, которое будет присвоено представляют максимальное число дней для выбора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761008), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl №&8;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]  
  
##  <a name="a-namesetmonthdeltaa--cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>CMonthCalCtrl::SetMonthDelta  
 Задает скорость прокрутки для элемента управления календаря на месяц.  
  
```  
int SetMonthDelta(int iDelta);
```  
  
### <a name="parameters"></a>Параметры  
 *iDelta*  
 Число месяцев в качестве скорость прокрутки элемента управления. Если это значение равно нулю, изменение количества месяцев сбрасывается в значение по умолчанию, — это количество месяцев, отображаемых в элементе управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие скорость прокрутки. Если скорость прокрутки не было задано ранее, возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb761010), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmonthviewa--cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>CMonthCalCtrl::SetMonthView  
 Задает элемент управления calendar текущего месяца для отображения представления месяца.  
  
```  
BOOL SetMonthView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод установить представление `MCMV_MONTH`, который представляет представление месяца.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_monthCalCtrl`, который используется для программного доступа к управляющий элемент календаря. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1 №&9;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает управляющий элемент календаря отображать месяц, год, десятилетия и представления века.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]  
  
##  <a name="a-namesetrangea--cmonthcalctrlsetrange"></a><a name="setrange"></a>CMonthCalCtrl::SetRange  
 Задает минимальное и максимальное допустимые даты для элемента управления календаря на месяц.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);

 
BOOL SetRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>Параметры  
 `pMinRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце нижнего диапазона.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структура, содержащая дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761012), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `SetRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
  В примере показано [CMonthCalCtrl::GetRange](#getrange).  
  
##  <a name="a-namesetselrangea--cmonthcalctrlsetselrange"></a><a name="setselrange"></a>CMonthCalCtrl::SetSelRange  
 Задает Выбор календарь на месяц элемента управления для указанного диапазона дат.  
  
```  
BOOL SetSelRange(
    const COleDateTime& pMinRange,  
    const COleDateTime& pMaxRange);

 
BOOL SetSelRange(
    const CTime& pMinRange,  
    const CTime& pMaxRange);

 
BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>Параметры  
 `pMinRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структура, содержащая дату в конце нижнего диапазона.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структура, содержащая дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761014), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC `SetSelRange`, можно указать `COleDateTime` использования, `CTime` использования, или `SYSTEMTIME` структуры использования.  
  
##  <a name="a-namesettodaya--cmonthcalctrlsettoday"></a><a name="settoday"></a>CMonthCalCtrl::SetToday  
 Задает элемент управления calendar за текущий день.  
  
```  
void SetToday(const COleDateTime& refDateTime);  
void SetToday(const CTime* pDateTime);  
  void SetToday(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Параметры  
 `refDateTime`  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, который содержит текущую дату.  
  
 `pDateTime`  
 Во второй версии указатель [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий сведения о текущей дате. В третьей версии указатель [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую сведения о текущей дате.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb761016), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CMonthCalCtrl::GetToday](#gettoday).  
  
##  <a name="a-namesetyearviewa--cmonthcalctrlsetyearview"></a><a name="setyearview"></a>CMonthCalCtrl::SetYearView  
 Задает текущий месяц календаря элемента управления представления года.  
  
```  
BOOL SetYearView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод установить представление `MCMV_YEAR`, представляющего ежегодное представление.  
  
##  <a name="a-namesizeminreqa--cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>CMonthCalCtrl::SizeMinReq  
 Отображает месяц, элемента календаря для минимального размера, отображает один месяц.  
  
```  
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRepaint`  
 Указывает, является ли элемент управления повторное окрашивание. По умолчанию **TRUE**. Если **FALSE**, обновление не происходит.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления calendar month изменяется в соответствии с минимальной; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов `SizeMinReq` успешно отображает элемент управления calendar целый месяц для одного месяца календаря.  
  
##  <a name="a-namesizerecttomina--cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>CMonthCalCtrl::SizeRectToMin  
 Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, содержащий все календари, которые помещаются в заданном прямоугольнике.  
  
```  
LPRECT SizeRectToMin(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `lpRect`|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определяющая прямоугольник, содержащий нужное число календарей.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определяющая прямоугольник, размер которых меньше или равно в прямоугольник, определяемый `lpRect` параметр.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет, сколько календарей умещается в прямоугольник, задаваемый параметром `lpRect` параметр и затем возвращает наименьший прямоугольник, который может содержать это число календарей. По сути этот метод к прямоугольнику указанного точно по размеру требуемое число календарей.  
  
 Этот метод отправляет [MCM_SIZERECTTOMIN](http://msdn.microsoft.com/library/windows/desktop/bb761020) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl-класс](../../mfc/reference/cdatetimectrl-class.md)


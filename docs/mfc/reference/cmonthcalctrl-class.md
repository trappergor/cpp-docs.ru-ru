---
title: CMonthCalCtrl-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45e0499297c814e4a214962bc2f51404960a8c38
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039223"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl-класс
Инкапсулирует функциональность элемента управления "календарь месяца".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Создает объект `CMonthCalCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](#create)|Создает элемент управления Календарь месяца и прикрепляет его к `CMonthCalCtrl` объекта.|  
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Получает ширину границы элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Возвращает число календарей, отображаемый в элементе управления календаря текущего месяца.|  
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Извлекает сведения об элементе управления календаря текущего месяца.|  
|[CMonthCalCtrl::GetCalID](#getcalid)|Извлекает идентификатор календаря для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetColor](#getcolor)|Возвращает цвет для заданной области элемента управления календаря на месяц.|  
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Возвращает представление, которое в текущий момент отображается элементом управления Календарь текущего месяца.|  
|[CMonthCalCtrl::GetCurSel](#getcursel)|Получает системное время, как указано в выбранной даты.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Возвращает первый день недели, отображаемый в левом столбце календаря.|  
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Извлекает текущее максимальное число дней, которые могут быть выбраны в элементе управления Календарь месяца.|  
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Возвращает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Возвращает минимальный размер, необходимый для отображения полного месяца в элементе управления календаря на месяц.|  
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Возвращает скорость прокрутки для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Извлекает даты сведения, представляющий высокой и низкой пределы отображения элемента управления calendar month.|  
|[CMonthCalCtrl::GetRange](#getrange)|Получает текущие даты минимальное и максимальное значение в элементе управления Календарь месяца.|  
|[CMonthCalCtrl::GetSelRange](#getselrange)|Извлекает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного в данный момент пользователь.|  
|[CMonthCalCtrl::GetToday](#gettoday)|Извлекает сведения о дате по дате, указанной как «сегодня» для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::HitTest](#hittest)|Определяет, какие части элемента управления календаря на месяц в заданной точке экрана.|  
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца века представления.|  
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десяти лет.|  
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.|  
|[CMonthCalCtrl::IsYearView](#isyearview)|Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.|  
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Задает ширину границы элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Задает ширину границы элемента управления calendar текущего месяца, по умолчанию.|  
|[CMonthCalCtrl::SetCalID](#setcalid)|Задает идентификатор календаря для элемента управления calendar текущего месяца.|  
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Задает элемент управления calendar текущего месяца для отображения представления века.|  
|[CMonthCalCtrl::SetColor](#setcolor)|Задает цвет заданную область элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Задает для элемента управления calendar текущего месяца для отображения указанного представления.|  
|[CMonthCalCtrl::SetCurSel](#setcursel)|Задает поле выбранную дату для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetDayState](#setdaystate)|Задает отображение дней в элементе управления Календарь месяца.|  
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Задает текущий месяц календаря элемента управления представления десяти лет.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Задает день недели, отображаемый в левом столбце календаря.|  
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Задает максимальное количество дней, которые могут быть выбраны в элементе управления Календарь месяца.|  
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Задает скорость прокрутки для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Задает элемент управления calendar текущего месяца для отображения в представлении «месяц».|  
|[CMonthCalCtrl::SetRange](#setrange)|Задает минимальное и максимальное допустимые даты для элемента управления календаря на месяц.|  
|[CMonthCalCtrl::SetSelRange](#setselrange)|Задает набор календарь на месяц элемента управления для указанного диапазона дат.|  
|[CMonthCalCtrl::SetToday](#settoday)|Задает элемент управления calendar за текущий день.|  
|[CMonthCalCtrl::SetYearView](#setyearview)|Задает текущий месяц календаря элемента управления представления года.|  
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Перерисовывает месячном календаре управление его размер, минимум, один месяц.|  
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, который может содержать все календари, которые помещаются в заданном прямоугольнике.|  
  
## <a name="remarks"></a>Примечания  
 Управляющий элемент календаря предоставляет пользователю интерфейс простой календаря, из которого пользователь может выбрать дату. Пользователь может изменить отображение по:  
  
-   Переход назад и вперед, от месяца к месяцу.  
  
-   Щелкнув сегодня текст для отображения текущего дня (если **MCS_NOTODAY** стиля не используется).  
  
-   Комплектации, месяц или год всплывающего меню.  
  
 Вы можете настроить месяц календаря элемента управления, применяя различные стили объекта при его создании. Эти стили описаны в [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919) в Windows SDK.  
  
 Управляющий элемент календаря можно отображать более чем один месяц, а также его можно указать специальные дни (например, в праздничные дни), полужирное начертание даты.  
  
 Дополнительные сведения об использовании управления Календарь месяца см. в разделе [использование CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdtctl.h  
  
##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl  
 Создает объект `CMonthCalCtrl`.  
  
```  
CMonthCalCtrl();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать **создать** после создания объекта.  
  
##  <a name="create"></a>  CMonthCalCtrl::Create  
 Создает элемент управления Календарь месяца и прикрепляет его к `CMonthCalCtrl` объекта.  
  
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
 *dwStyle*  
 Задает сочетание Windows стили, примененные к элементу управления Календарь месяца. В разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919) в Windows SDK, Дополнительные сведения о стилях.  
  
 *Rect*  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры. Содержит положение и размер элемента управления calendar month.  
  
 *pt*  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру, которая определяет расположение элемента управления Календарь месяца.  
  
 *pParentWnd*  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления calendar month. Он не должен быть **NULL**.  
  
 *nID*  
 Указывает идентификатор элемента управления calendar month элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создание месяц календаря управления в два этапа:  
  
1.  Вызовите [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) для создания `CMonthCalCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает управления Календарь месяца и прикрепляет его к `CMonthCalCtrl` объекта.  
  
 При вызове `Create`, инициализируются стандартных элементов управления. Версия `Create` вы вызова определяет способ изменения размеров:  
  
-   Чтобы MFC автоматическое изменение размера элемента управления в один месяц, вызовите переопределения, которое использует *pt* параметра.  
  
-   Изменение размера элемента управления самостоятельно, вызовет переопределение этой функции, который использует *rect* параметра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]  
  
##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder  
 Получает ширину границы элемента управления calendar текущего месяца.  
  
```  
int GetCalendarBorder() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина границы элемента управления, в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760945) сообщение, которое описано в Windows SDK.  
  
##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount  
 Возвращает число календарей, отображаемый в элементе управления календаря текущего месяца.  
  
```  
int GetCalendarCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество календарей, отображаемый в текущий момент в элементе управления календаря на месяц. Максимально допустимое число календарей — 12.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760947) сообщение, которое описано в Windows SDK.  
  
##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo  
 Извлекает сведения об элементе управления календаря текущего месяца.  
  
```  
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[out] *pmcGridInfo*|Указатель на [MCGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760925) структуры, который получает сведения об элементе управления календаря текущего месяца. Вызывающий объект отвечает за выделение и инициализации этой структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCALENDARGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760949) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 Следующий пример кода использует `GetCalendarGridInfo` метод для извлечения календарная дата, отображаются в элементе управления календаря текущего месяца.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]  
  
##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID  
 Извлекает идентификатор календаря для элемента управления calendar текущего месяца.  
  
```  
CALID GetCalID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из [идентификатор календаря](http://msdn.microsoft.com/library/windows/desktop/dd317732) константы.  
  
### <a name="remarks"></a>Примечания  
 Обозначает идентификатор календаря календаре конкретного региона, например григорианский (локализованный), японский или хиджра календари. Приложение может использовать идентификатор календаря, который имеет поддержка функции различных языков.  
  
 Этот метод отправляет [MCM_GETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760951) сообщение, которое описано в Windows SDK.  
  
##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor  
 Получает цвет области месяца календаря управления, указанный в *nRegion*.  
  
```  
COLORREF GetColor(int nRegion) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nRegion*  
 Область управления Календарь месяца, из которого извлекается цвет. Список значений см. в разделе *nRegion* параметр [SetColor](#setcolor).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, указывающее цвет, связанный с частью управления Календарь месяца, в случае успешного выполнения. В противном случае эта функция-член возвращает значение -1.  
  
##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView  
 Возвращает представление, которое в текущий момент отображается элементом управления Календарь текущего месяца.  
  
```  
DWORD GetCurrentView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее представление, которое указывается одним из следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|`MCMV_MONTH`|Месячное представление|  
|`MCMV_YEAR`|Ежегодное представление|  
|`MCMV_DECADE`|Представление десяти лет|  
|`MCMV_CENTURY`|Представление века|  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 Следующие отчеты пример кода, которые просмотреть календарь месяца сейчас управлять отображением.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]  
  
##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel  
 Получает системное время, как указано в выбранной даты.  
  
```  
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;  
   
BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *refDateTime*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта. Получает текущее время.  
  
 *pDateTime*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет получать сведения о выбранной дате. Этот параметр должен быть допустимый адрес и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; otherwize 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb760957), как описано в Windows SDK.  
  
> [!NOTE]
>  Эта функция-член не выполняется, если стиль **MCS_MULTISELECT** имеет значение.  
  
 В реализации MFC `GetCurSel`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek  
 Возвращает первый день недели, отображаемый в левом столбце календаря.  
  
```  
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pbLocal*  
 Указатель на **BOOL** значение. Если значение равно нулю, значение элемента управления не соответствует параметру в панели управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее первый день недели. В разделе **примечания** Дополнительные сведения о представляют эти целых чисел.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb760958), как описано в Windows SDK. Дни недели, представляются в виде целых чисел, следующим образом.  
  
|Значение|День недели|  
|-----------|---------------------|  
|0|понедельник|  
|1|Вторник|  
|2|среда|  
|3|Четверг|  
|4|пятница|  
|5|Суббота|  
|6|Воскресенье|  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).  
  
##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount  
 Извлекает текущее максимальное число дней, которые могут быть выбраны в элементе управления Календарь месяца.  
  
```  
int GetMaxSelCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее общее число дней, которые могут быть выбраны для элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760960), как описано в Windows SDK. Используйте эту функцию-член для элементов управления с **MCS_MULTISELECT** стиля набора.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).  
  
##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth  
 Возвращает максимальную ширину строки «Сегодня» для элемента управления calendar текущего месяца.  
  
```  
DWORD GetMaxTodayWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина «Сегодня» строки в пикселях.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано `GetMaxTodayWidth` метод.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]  
  
### <a name="remarks"></a>Примечания  
 Пользователь может возвращать на текущую дату, щелкнув строку «Сегодня», которая отображается в нижней части элемента управления Календарь месяца. Строка «Сегодня» содержит текст дату и метку.  
  
 Этот метод отправляет [MCM_GETMAXTODAYWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760962) сообщение, которое описано в Windows SDK.  
  
##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect  
 Возвращает минимальный размер, необходимый для отображения полного месяца в элементе управления календаря на месяц.  
  
```  
BOOL GetMinReqRect(RECT* pRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pRect*  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру, которая будет получать сведения ограничивающего прямоугольника. Этот параметр должен быть допустимый адрес и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном завершении, эта функция-член возвращает ненулевое значение, и `lpRect` Получает ограничивающий данные. Если операция завершилась неудачей, функция-член возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMINREQRECT](http://msdn.microsoft.com/library/windows/desktop/bb760978), как описано в Windows SDK.  
  
##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta  
 Возвращает скорость прокрутки для элемента управления календаря на месяц.  
  
```  
int GetMonthDelta() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Скорость прокрутки для элемента управления calendar month. Скорость прокрутки — количество месяцев, что элемент управления перемещается его отображения, когда пользователь нажимает кнопку прокрутки один раз.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb760980), как описано в Windows SDK.  
  
##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange  
 Извлекает даты сведения, представляющий высокой и низкой пределы отображения элемента управления calendar month.  
  
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
 *refMinRange*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальное даты, допустимое.  
  
 *refMaxRange*  
 Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.  
  
 *pMinRange*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце нижнего диапазона.  
  
 *pMaxRange*  
 Указатель на `SYSTEMTIME` структуру, содержащую дату в конце наибольший диапазон.  
  
 *dwFlags*  
 Значение, указывающее область границы диапазона, который требуется получить. Это значение должно быть одно из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|GMR_DAYSTATE|Включить предшествующий и в конце месяца видимого диапазона, отображаются только частично.|  
|GMR_VISIBLE|Включать только эти месяцы, которые отображаются полностью.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Integer, представляющее диапазона, в месяцах, занимаемых двух ограничений обозначается *refMinRange* и *refMaxRange* в версиях первого и второго или *pMinRange* и *pMaxRange* в третьей версии.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETMONTHRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760981), как описано в Windows SDK. В реализации MFC `GetMonthRange`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMonthCalCtrl::SetDayState](#setdaystate).  
  
##  <a name="getrange"></a>  CMonthCalCtrl::GetRange  
 Получает текущие даты минимальное и максимальное значение в элементе управления Календарь месяца.  
  
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
 *pMinRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце нижнего диапазона.  
  
 *pMaxRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` , может быть равен нулю (без ограничения задаются) или сочетанием следующих значений, указанных сведений об ограничениях.  
  
|Значение|Значение|  
|-----------|-------------|  
|GDTR_MAX|Максимальное значение задано для элемента управления; *pMaxRange* является допустимым и содержит сведения о применимых дате.|  
|GDTR_MIN|Нижний предел задается для элемента управления. *pMinRange* является допустимым и содержит сведения о применимых дате.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760983), как описано в Windows SDK. В реализации MFC `GetRange`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]  
  
##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange  
 Извлекает сведения о датах, представляющий верхний и нижний пределы диапазона дат, выбранного в данный момент пользователь.  
  
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
 *refMinRange*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий минимальное даты, допустимое.  
  
 *refMaxRange*  
 Ссылку на `COleDateTime` или `CTime` объект, содержащий Максимальная допустимая дата.  
  
 *pMinRange*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце нижнего диапазона.  
  
 *pMaxRange*  
 Указатель на `SYSTEMTIME` структуру, содержащую дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760985), как описано в Windows SDK. `GetSelRange` завершится ошибкой, если применяется к элементу управления Календарь месяца, который не использует **MCS_MULTISELECT** стиля.  
  
 В реализации MFC `GetSelRange`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday  
 Извлекает сведения о дате по дате, указанной как «сегодня» для элемента управления календаря на месяц.  
  
```  
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;  
   
BOOL GetToday(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *refDateTime*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , показывающий текущий день.  
  
 *pDateTime*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет получать сведения о дате. Этот параметр должен быть допустимый адрес и не может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_GETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb760987), как описано в Windows SDK. В реализации MFC `GetToday`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]  
  
##  <a name="hittest"></a>  CMonthCalCtrl::HitTest  
 Определяет какой управляющий элемент календаря, если он имеется в указанной позиции.  
  
```  
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```  
  
### <a name="parameters"></a>Параметры  
 *pMCHitTest*  
 Указатель на [MCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760927) структуру, содержащую попадания точки для управления Календарь месяца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `DWORD`. Равно **uHit** членом **MCHITTESTINFO** структуры.  
  
### <a name="remarks"></a>Примечания  
 `HitTest` использует **MCHITTESTINFO** структуру, которая содержит сведения о проверки нажатия.  
  
##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца века представления.  
  
```  
BOOL IsCenturyView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущим представлением является века представления; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщение, которое описано в Windows SDK. Если сообщения, которое возвращает `MCMV_CENTURY`, этот метод возвращает `true`.  
  
##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление десяти лет.  
  
```  
BOOL IsDecadeView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущим представлением является десятилетия представления; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщение, которое описано в Windows SDK. Если сообщения, которое возвращает `MCMV_DECADE`, этот метод возвращает `true`.  
  
##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление месяца.  
  
```  
BOOL IsMonthView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущим представлением является месяц; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщение, которое описано в Windows SDK. Если сообщения, которое возвращает `MCMV_MONTH`, этот метод возвращает `true`.  
  
##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView  
 Указывает, является ли текущее представление элемента управления calendar текущего месяца представление года.  
  
```  
BOOL IsYearView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущим представлением является представления года; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) сообщение, которое описано в Windows SDK. Если сообщения, которое возвращает `MCMV_YEAR`, этот метод возвращает `true`.  
  
##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder  
 Задает ширину границы элемента управления calendar текущего месяца.  
  
```  
void SetCalendarBorder(int cxyBorder);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *cxyBorder*|Ширина границы в пикселях.|  
  
### <a name="remarks"></a>Примечания  
 Если этот метод завершается успешно, ширину границы присваивается *cxyBorder* параметра. В противном случае ширину границы сбрасывается в значение по умолчанию, которая указана в текущем [темы](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), или нуль, если темы не используются.  
  
 Этот метод отправляет [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается ширину границы в месячном календаре управления до восьми пикселей. Используйте [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) метод, чтобы определить, является ли этот метод успешно выполнен.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]  
  
##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault  
 Задает ширину границы элемента управления calendar текущего месяца, по умолчанию.  
  
```  
void SetCalendarBorderDefault();
```  
  
### <a name="remarks"></a>Примечания  
 Ширина границы задано значение по умолчанию, указанное текущим [темы](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), или нуль, если темы не используются.  
  
 Этот метод отправляет [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) сообщение, которое описано в Windows SDK.  
  
##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID  
 Задает идентификатор календаря для элемента управления calendar текущего месяца.  
  
```  
BOOL SetCalID(CALID calid);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *calid*|Один из [идентификатор календаря](http://msdn.microsoft.com/library/windows/desktop/dd317732) константы.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Указывает идентификатор календаря, календаре конкретного региона, например григорианский (локализованный), японский или хиджра календари. Используйте `SetCalID` метод для отображения календаря, который задается параметром *calid* параметра, если на компьютере установлен языковой стандарт с календарем.  
  
 Этот метод отправляет [MCM_SETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760995) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает управления Календарь месяца для отображения императора японского календаря. `SetCalID` Метод завершается успешно только в том случае, если этот календарь, установленной на компьютере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]  
  
##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView  
 Задает элемент управления calendar текущего месяца для отображения представления века.  
  
```  
BOOL SetCenturyView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_CENTURY`, представляющий представление века.  
  
##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor  
 Задает цвет заданную область элемента управления календаря на месяц.  
  
```  
COLORREF SetColor(
    int nRegion,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 *nRegion*  
 Целочисленное значение, задающее цвет календаря какие месяц для задания. Это значение может быть одно из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|MCSC_BACKGROUND|Фоновый цвет, отображаемый между месяцами.|  
|MCSC_MONTHBK|Фоновый цвет, отображаемый в области месяца.|  
|MCSC_TEXT|Цвет, используемый для отображения текста в течение месяца.|  
|MCSC_TITLEBK|Фоновый цвет, отображаемый в заглавии календаря.|  
|MCSC_TITLETEXT|Цвет, используемый для отображения текста в заглавии календаря.|  
|MCSC_TRAILINGTEXT|Цвет, используемый для отображения текста заголовка и в конце дня. Завершающие и начальные дни-это дни предыдущего и следующего месяца, отображаемые на текущий календарь.|  
  
 *ref*  
 Объект **COLORREF** значение параметра новый цвет для указанного фрагмента управления Календарь месяца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее предыдущей настройки цвета для указанного фрагмента управления Календарь месяца, в случае успешного выполнения. В противном случае оно возвращает значение -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760997), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]  
  
##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView  
 Задает для элемента управления calendar текущего месяца для отображения указанного представления.  
  
```  
BOOL SetCurrentView(DWORD dwNewView);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *dwNewView*|Одно из следующих значений, указывающее ежемесячно, годовой десятилетия или века представления.<br /><br /> MCMV_MONTH: Представление месячного<br /><br /> MCMV_YEAR: Ежегодное представление<br /><br /> MCMV_DECADE: Представление десятилетия<br /><br /> MCMV_CENTURY: Представление века|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [MCM_SETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760998) сообщение, которое описано в Windows SDK.  
  
##  <a name="setcursel"></a>  CMonthCalCtrl::SetCurSel  
 Задает поле выбранную дату для элемента управления календаря на месяц.  
  
```  
BOOL SetCurSel(const COleDateTime& refDateTime);  
BOOL SetCurSel(const CTime& refDateTime);  
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Параметры  
 *refDateTime*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , показывающий выбранной управляющий элемент календаря.  
  
 *pDateTime*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в качестве текущего выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb761002), как описано в Windows SDK. В реализации MFC `SetCurSel`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]  
  
##  <a name="setdaystate"></a>  CMonthCalCtrl::SetDayState  
 Задает отображение дней в элементе управления Календарь месяца.  
  
```  
BOOL SetDayState(
    int nMonths,  
    LPMONTHDAYSTATE pStates);
```  
  
### <a name="parameters"></a>Параметры  
 *nMonths*  
 Значение, указывающее, какое количество элементов в массиве, *pStates* указывает.  
  
 *pStates*  
 Указатель на [MONTHDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760915) массив значений, определяющих способ рисования управления Календарь месяца каждый день в его отображении. **MONTHDAYSTATE** тип данных представляет собой битовое поле, где каждый бит (от 1 до 31) представляет состояние дня в месяце. Если бит включен, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться с без выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761004), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]  
  
##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView  
 Задает текущий месяц календаря элемента управления представления десяти лет.  
  
```  
BOOL SetDecadeView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_DECADE`, которой представляет представление десяти лет.  
  
##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek  
 Задает день недели, отображаемый в левом столбце календаря.  
  
```  
BOOL SetFirstDayOfWeek(
    int iDay,  
    int* lpnOld = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *iDay*  
 Целое число, представляющее день — должен быть задан как первый день недели. Это значение должно быть одним из номеров день. В разделе [GetFirstDayOfWeek](#getfirstdayofweek) описание номера дня.  
  
 *lpnOld*  
 Установите указатель на целое число, указывающее первый день недели, ранее.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если предыдущий первый день недели присвоено значение, отличным от типа **LOCALE_IFIRSTDAYOFWEEK**, являющееся день, указанный в параметр панели управления. В противном случае эта функция возвращает 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb761006), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]  
  
##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount  
 Задает максимальное количество дней, которые могут быть выбраны в элементе управления Календарь месяца.  
  
```  
BOOL SetMaxSelCount(int nMax);
```  
  
### <a name="parameters"></a>Параметры  
 *nMax*  
 Значение, которое будет присвоено представляет максимальное число дней, доступный для выбора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761008), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]  
  
##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta  
 Задает скорость прокрутки для элемента управления календаря на месяц.  
  
```  
int SetMonthDelta(int iDelta);
```  
  
### <a name="parameters"></a>Параметры  
 *класса iDelta*  
 Число месяцев, должен быть задан как скорость прокрутки элемента управления. Если это значение равно нулю, изменение количества месяцев сбрасываются до значений по умолчанию число месяцев, отображаемых в элементе управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие скорость прокрутки. Если скорость прокрутки не было задано ранее, возвращаемое значение — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb761010), как описано в Windows SDK.  
  
##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView  
 Задает элемент управления calendar текущего месяца для отображения в представлении «месяц».  
  
```  
BOOL SetMonthView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_MONTH`, который представляет представление месяца.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_monthCalCtrl`, который используется для программного доступа к управления Календарь месяца. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задает управления Календарь месяца для отображения месяца, года, десяти лет и века представления.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]  
  
##  <a name="setrange"></a>  CMonthCalCtrl::SetRange  
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
 *pMinRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце нижнего диапазона.  
  
 *pMaxRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структуру, содержащую дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761012), как описано в Windows SDK. В реализации MFC `SetRange`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMonthCalCtrl::GetRange](#getrange).  
  
##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange  
 Задает набор календарь на месяц элемента управления для указанного диапазона дат.  
  
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
 *pMinRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую дату в конце нижнего диапазона.  
  
 *pMaxRange*  
 Указатель на `COleDateTime` объекта, `CTime` объекта, или `SYSTEMTIME` структуру, содержащую дату в конце наибольший диапазон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761014), как описано в Windows SDK. В реализации MFC `SetSelRange`, можно указать `COleDateTime` использования, `CTime` использование, или `SYSTEMTIME` структуры использования.  
  
##  <a name="settoday"></a>  CMonthCalCtrl::SetToday  
 Задает элемент управления calendar за текущий день.  
  
```  
void SetToday(const COleDateTime& refDateTime);  
void SetToday(const CTime* pDateTime);  
  void SetToday(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Параметры  
 *refDateTime*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, который содержит текущую дату.  
  
 *pDateTime*  
 Во второй версии указатель [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий сведения о текущей дате. В третьей версии указатель [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую сведения о текущей дате.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [MCM_SETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb761016), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMonthCalCtrl::GetToday](#gettoday).  
  
##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView  
 Задает текущий месяц календаря элемента управления представления года.  
  
```  
BOOL SetYearView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод использует [CMonthCalCtrl::SetCurrentView](#setcurrentview) метод, чтобы задать представление `MCMV_YEAR`, который представляет годовые представления.  
  
##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq  
 Отображает месяц, элемента календаря для минимального размера, отображается один месяц.  
  
```  
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bRepaint*  
 Указывает, является ли элемент управления повторное окрашивание. По умолчанию **TRUE**. Если **FALSE**, перерисовка не происходит.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если размер элемента управления Календарь месяца для минимального; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов `SizeMinReq` успешно отображает весь управляющий элемент календаря для одного месяца календаря.  
  
##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin  
 Для элемента управления calendar текущего месяца вычисляет наименьший прямоугольник, который может содержать все календари, которые помещаются в заданном прямоугольнике.  
  
```  
LPRECT SizeRectToMin(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *lpRect*|Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определяющая прямоугольник, содержащий нужное число календарей.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определяющая прямоугольник, размер которых меньше или равно в прямоугольник, определяемый *lpRect* параметра.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вычисляет, сколько календарей помещается в прямоугольник, задаваемый параметром *lpRect* параметра и затем возвращает наименьшее прямоугольник, который может содержать это число календарей. По сути этот метод к прямоугольнику указанного точно по размеру требуемое число календарей.  
  
 Этот метод отправляет [MCM_SIZERECTTOMIN](http://msdn.microsoft.com/library/windows/desktop/bb761020) сообщение, которое описано в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)

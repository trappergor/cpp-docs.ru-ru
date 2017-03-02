---
title: "CDateTimeCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], CDateTimeCtrl class
- date-picking functionality
- CDateTimeCtrl class
- DateTimePicker control [MFC]
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
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
ms.openlocfilehash: e5407934021abdb64dfb625e3dfb2c1841b7a5f0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl-класс
Инкапсулирует функциональность элемента управления "выбор даты и времени".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Создает объект `CDateTimeCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Закрывает текущий элемент управления выбора даты и времени.|  
|[CDateTimeCtrl::Create](#create)|Создает элемент управления для выбора даты и времени и присоединяет его к `CDateTimeCtrl` объекта.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Извлекает сведения о текущей управления выбора даты и времени.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Возвращает идеального размера элемента управления выбора даты и времени, необходимого для отображения текущей даты или времени.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Получает цвет для данной части календарного месяца в элементе управления выбора даты и времени.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Извлекает `CMonthCalCtrl` объект, связанный с элементом управления выбора даты и времени.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Получает шрифт, используемый в настоящее время, Дата и месяц календаря элемента управления выбора времени дочернего элемента управления.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Возвращает стиль текущего элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::GetRange](#getrange)|Получает текущий минимальное и максимальное допустимое время системы управления выбора даты и времени.|  
|[CDateTimeCtrl::GetTime](#gettime)|Получает выбранный в данный момент времени из элемент выбора даты и времени и помещает его в указанном `SYSTEMTIME` структуры.|  
|[CDateTimeCtrl::SetFormat](#setformat)|Задает отображение элемент выбора даты и времени в соответствии с строка данного формата.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Задает цвет для данной части календарного месяца в элементе управления выбора даты и времени.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Задает шрифт, используемый месяц календаря дату и время выбора элемента управления дочернего элемента управления.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Задает стиль текущего элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::SetRange](#setrange)|Задает минимальное и максимальное допустимые системное время для элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::SetTime](#settime)|Задает время в элемент управления выбора даты и времени.|  
  
## <a name="remarks"></a>Примечания  
 Дата и время выбора элемент управления (DTP) предоставляет простой интерфейс для обмена данными даты и времени с пользователем. Этот интерфейс содержит поля, каждый из которых отображает часть данных даты и времени хранятся в элементе управления. Пользователь может изменить сведения, хранящиеся в элементе управления изменение содержимого строки в данном поле. Пользователь может перемещаться между полями с помощью мыши или клавиатуры.  
  
 Можно настроить элемент управления для выбора даты и времени, применяя различные стили к объекту при его создании. В разделе [стили даты и времени выбора элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761728) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о стилях, специфическое для элемента управления выбора даты и времени. Можно задать формат отображения с помощью стилей форматирования ВНУТРИ элемента управления. Эти стили, описаны в разделе «Стили» в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)] разделе [стили даты и времени выбора элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Элемент управления для выбора даты и времени также использует уведомления и обратные вызовы, которые описаны в [CDateTimeCtrl с помощью](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdtctl.h  
  
##  <a name="a-namecdatetimectrla--cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Создает объект `CDateTimeCtrl`.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="a-nameclosemonthcala--cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Закрывает текущий элемент управления выбора даты и времени.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода закрывает раскрывающегося календаря для текущего элемента управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="a-namecreatea--cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Create  
 Создает элемент управления для выбора даты и времени и присоединяет его к `CDateTimeCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стилей элемента управления даты времени. В разделе [стили даты и времени выбора элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb761728) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о стилях выбора даты и времени.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер элемента управления выбора даты и времени.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления выбора даты и времени. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления датой и временем выбора элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если создание выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Чтобы создать элемент выбора даты и времени  
  
1.  Вызов [CDateTimeCtrl](#cdatetimectrl) для создания `CDateTimeCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает управления выбора даты и времени в Windows и присоединяет его к `CDateTimeCtrl` объекта.  
  
 При вызове **создать**, общие элементы управления инициализируются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="a-namegetdatetimepickerinfoa--cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Извлекает сведения о текущей управления выбора даты и времени.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `pDateTimePickerInfo`|Указатель на [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) структуру, которая получает описание текущего элемента управления выбора даты и времени.<br /><br /> Вызывающий объект отвечает за выделение этой структуры. Тем не менее, этот метод инициализирует `cbSize` член структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода указывает ли успешно получает сведения о текущей управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="a-namegetmonthcalcolora--cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Получает цвет для данной части календарного месяца в элементе управления выбора даты и времени.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `iColor`  
 `int` Значение, указывающее, какой цвет области месячный календарь для извлечения. Список значений см. в разделе `iColor` параметр [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее указанную часть элемента управления calendar month цветопередачи при успешном выполнении. Функция возвращает -1, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="a-namegetmonthcalctrla--cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 Извлекает `CMonthCalCtrl` объект, связанный с элементом управления выбора даты и времени.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) объекта, или **NULL** в случае неудачи, или если окно не отображается.  
  
### <a name="remarks"></a>Примечания  
 Элементы управления выбора даты и времени создания календарного месяца дочернего элемента управления при щелчке стрелки раскрывающегося списка. Если `CMonthCalCtrl` объект больше не нужен, он будет уничтожен, поэтому приложения не должны полагаться на объект, представляющий календарь на месяц дочерних управления выбора даты времени хранения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="a-namegetmonthcalfonta--cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Возвращает шрифт, используемый в настоящее время, Дата и управляющий элемент выбора времени элемента управления календаря.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CFont](../../mfc/reference/cfont-class.md) объекта, или **NULL** в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 `CFont` Объект, на который указывает возвращаемое значение является временным и уничтожается во время следующей обработки времени простоя.  
  
##  <a name="a-namegetmonthcalstylea--cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Получает стиль элемента управления calendar month раскрывающийся список, связанный с текущего элемента управления выбора даты и времени.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль элемента управления calendar месяц раскрывающегося списка, которое представляет собой побитовое сочетание (или) стилей элемента управления выбора даты и времени. Дополнительные сведения см. в разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrangea--cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl::GetRange  
 Получает текущий минимальное и максимальное допустимое время системы управления выбора даты и времени.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pMinRange`  
 Указатель на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий самое раннее время, разрешенных в `CDateTimeCtrl` объекта.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта или `CTime` объект, содержащий самое позднее время, разрешенных в `CDateTimeCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` значение, содержащее флаги, указывающие, какие диапазоны задаются. If  
  
 `return value & GDTR_MAX` == 0  
  
 Второй параметр является допустимым. Аналогично Если  
  
 `return value & GDTR_MIN` == 0  
  
 Первый параметр является допустимым.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC можно указать `COleDateTime` или `CTime` использования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="a-namegettimea--cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime  
 Получает выбранный в данный момент времени из элемент выбора даты и времени и помещает его в указанном `SYSTEMTIME` структуры.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *timeDest*  
 В первой версии ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о системе времени. Во второй версии ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о системе времени.  
  
 *pTimeDest*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведений о системе времени. Не должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой версии ненулевое значение, если время успешно записан `COleDateTime` объекта; в противном случае — 0. В версиях второго и третьего `DWORD` значение, равное **dwFlag** набор элементов [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры. В разделе **примечания** Дополнительные сведения в приведенном ниже разделе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC **GetTime**, можно использовать `COleDateTime` или `CTime` классов, или же можно использовать `SYSTEMTIME` структуры для хранения сведений о времени.  
  
 Возвращаемое значение `DWORD` в версиях второй и третий выше, указывает ли элемент управления для выбора даты и времени присвоено состояние «не date», как указано в [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) член структуры `dwFlags`. Если возвращаемое значение равно **GDT_NONE**, элемент управления присваивается состояние «Нет даты» и использует **DTS_SHOWNONE** стиля. Если возвращаемое значение равно **GDT_VALID**, системное время успешно сохранен в месте назначения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Возвращает идеального размера элемента управления выбора даты и времени, необходимого для отображения текущей даты или времени.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[выходной] `psize`|Указатель на [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуру, содержащую идеального размера для элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение всегда равно `true`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекается наилучший размер для отображения элемента управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="a-namesetformata--cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::SetFormat  
 Задает отображение элемент выбора даты и времени в соответствии с строка данного формата.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Параметры  
 *pstrFormat*  
 Указатель на формат нулем строка, которая определяет нужную форму. Установка этого параметра на **NULL** сбросит строка формата по умолчанию для текущего стиля элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
> [!NOTE]
>  Ввод данных пользователем не определить, успех или неудачу для этого вызова.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl №&6;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="a-namesetmonthcalcolora--cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Задает цвет для данной части календарного месяца в элементе управления выбора даты и времени.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 `iColor`  
 `int`значение, указывающее, какую область элемента управления calendar month для задания. Это значение может быть одно из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|MCSC_BACKGROUND|Задайте цвет фона между месяцев.|  
|MCSC_MONTHBK|Задайте фоновый цвет, отображаемый в течение месяца.|  
|MCSC_TEXT|Задайте цвет, используемый для отображения текста в течение месяца.|  
|MCSC_TITLEBK|Задайте цвет фона заголовка календаря.|  
|MCSC_TITLETEXT|Задайте цвет, используемый для отображения текста в пределах заголовка календаря.|  
|MCSC_TRAILINGTEXT|Задайте цвет, используемый для отображения заголовка и текста в конце дня. Завершающие и начальные дни-это дни предыдущего и последующего месяцев, которые отображаются на текущем календаре.|  
  
 `ref`  
 Объект **COLORREF** значение, представляющее цвет, который будет установлен для заданной области месячном календаре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее указанную часть элемента управления calendar month предыдущее значение цвета в случае успешного выполнения. В противном случае — сообщение возвращает -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="a-namesetmonthcalfonta--cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 Задает шрифт, используемый месяц календаря дату и время выбора элемента управления дочернего элемента управления.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hFont`  
 Дескриптор шрифта, которая будет задана.  
  
 `bRedraw`  
 Указывает, следует ли при настройке шрифта немедленно перерисовке элемента управления. Установка этого параметра на **TRUE** вызывает перерисовку элементом управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#7;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Если вы используете этот код, может потребоваться сделать членом вашей `CDialog`-производный класс с именем `m_MonthFont` типа **CFont**.  
  
##  <a name="a-namesetmonthcalstylea--cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Задает стиль элемента управления calendar month раскрывающийся список, связанный с текущего элемента управления выбора даты и времени.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwStyle`|Новый месяц календаря стиля элемента управления, которое представляет собой побитовое сочетание (или) стили элемента управления calendar month. Дополнительные сведения см. в разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие стиль элемента управления calendar month раскрывающегося списка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) сообщения, которое описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная, `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается управления выбора даты и времени для отображения номера недель, сокращенные названия дней недели, а не сегодня индикатора.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="a-namesetrangea--cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::SetRange  
 Задает минимальное и максимальное допустимые системное время для элемента управления выбора даты и времени.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>Параметры  
 `pMinRange`  
 Указатель на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий самое раннее время, разрешенных в `CDateTimeCtrl` объекта.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта или `CTime` объект, содержащий самое позднее время, разрешенных в `CDateTimeCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC можно указать `COleDateTime` или `CTime` использования. Если `COleDateTime` объект имеет **NULL** состояние, диапазон будут удалены. Если `CTime` указателя или `COleDateTime` указатель **NULL**, диапазон будут удалены.  
  
### <a name="example"></a>Пример  
  В примере показано [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="a-namesettimea--cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::SetTime  
 Задает время в элемент управления выбора даты и времени.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *timeNew*  
 Ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий для которого будет установить элемент управления.  
  
 *pTimeNew*  
 Во второй версии выше указатель [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий время, к которому будет установить элемент управления. В третьей версии выше указатель [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, содержащую время, к которому будет установить элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В реализации MFC **SetTime**, можно использовать `COleDateTime` или `CTime` классов, или же можно использовать `SYSTEMTIME` структуры, чтобы задать сведения о времени.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl №&8;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl-класс](../../mfc/reference/cmonthcalctrl-class.md)


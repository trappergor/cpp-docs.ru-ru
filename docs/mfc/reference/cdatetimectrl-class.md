---
title: "CDateTimeCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
dev_langs: C++
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3359b506217d2828207e06341fbf1fe53b3c0719
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl-класс
Инкапсулирует функциональность элемента управления "выбор даты и времени".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Создает объект `CDateTimeCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Закрывает текущий элемент управления выбора даты и времени.|  
|[CDateTimeCtrl::Create](#create)|Создает элемент управления выбора даты и времени и прикрепляет его к `CDateTimeCtrl` объекта.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Извлекает сведения о текущего элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Возвращает идеальный размер элемента управления выбора даты и времени, необходимого для отображения текущей даты или времени.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Получает цвет для данной части календарь месяца в элементе управления выбора даты и времени.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Извлекает `CMonthCalCtrl` объект, связанный с элементом управления выбора даты и времени.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Возвращает шрифт, используемый в настоящее время, Дата и управления Календарь месяца дочернего элемента управления выбора времени.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Возвращает стиль текущего элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::GetRange](#getrange)|Извлекает текущий минимальное и максимальное допустимое системное время для элемент выбора даты и времени.|  
|[CDateTimeCtrl::GetTime](#gettime)|Получает текущий выбранный времени из элемент выбора даты и времени и помещает его в указанном `SYSTEMTIME` структуры.|  
|[CDateTimeCtrl::SetFormat](#setformat)|Задает отображение элемент выбора даты и времени в соответствии с указанным форматом строка.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Задает цвет для данной части календарь месяца в элементе управления выбора даты и времени.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Задает шрифт, который будет использовать управления Календарь месяца дочерних даты и времени выбора элемента управления.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Задает стиль текущего элемента управления выбора даты и времени.|  
|[CDateTimeCtrl::SetRange](#setrange)|Задает минимальное и максимальное допустимые системное время для элемент выбора даты и времени.|  
|[CDateTimeCtrl::SetTime](#settime)|Задает время в элемент выбора даты и времени.|  
  
## <a name="remarks"></a>Примечания  
 Средстве выбора даты и времени (элемент управления DTP) предоставляет простой интерфейс для обмена данными даты и времени с пользователем. Этот интерфейс содержит поля, каждый из которых отображает часть сведений о дате и времени, хранятся в элементе управления. Пользователь может изменить сведения, хранящиеся в элементе управления изменение содержимого строки в данном поле. Можно перемещаться между полями с помощью клавиатуры или мыши.  
  
 Можно настроить элемент управления выбора даты и времени, применяя различные стили для объекта при его создании. В разделе [стили даты и времени выбора управления](http://msdn.microsoft.com/library/windows/desktop/bb761728) в Windows SDK, Дополнительные сведения о стилях, относящееся к элементу управления выбора даты и времени. Можно задать формат отображения элемента управления DTP, с помощью стилей форматирования. Эти стили форматирования описаны в разделе «Стили» в разделе Windows SDK [стили даты и времени выбора управления](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Уведомления и обратные вызовы, которые описаны в средстве выбора даты и времени также использует [использование CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Создает объект `CDateTimeCtrl`.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Закрывает текущий элемент управления выбора даты и времени.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода Закрытие раскрывающегося календаря для текущего элемента управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>CDateTimeCtrl::Create  
 Создает элемент управления выбора даты и времени и прикрепляет его к `CDateTimeCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает сочетание стилей элемента управления даты времени. В разделе [стили даты и времени выбора управления](http://msdn.microsoft.com/library/windows/desktop/bb761728) в Windows SDK, Дополнительные сведения о стилях выбора даты и времени.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, которая является положение и размер элемента управления выбора даты и времени.  
  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления выбора даты и времени. Он не должен быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления даты и времени выбора элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если создание прошло успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Чтобы создать элемент выбора даты и времени  
  
1.  Вызовите [CDateTimeCtrl](#cdatetimectrl) для создания `CDateTimeCtrl` объекта.  
  
2.  Вызовите эту функцию-член, который создает управления выбора даты и времени в Windows и прикрепляет его к `CDateTimeCtrl` объекта.  
  
 При вызове **создать**, инициализируются стандартных элементов управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Извлекает сведения о текущего элемента управления выбора даты и времени.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[выходной] `pDateTimePickerInfo`|Указатель на [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) структуру, которая получает описание текущего элемента управления выбора даты и времени.<br /><br /> Вызывающий объект отвечает за выделение этой структуры. Тем не менее, этот метод инициализирует `cbSize` член структуры.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода указывает, является ли она успешно извлекает сведения о текущего элемента управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Получает цвет для данной части календарь месяца в элементе управления выбора даты и времени.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `iColor`  
 `int` Значение, указывающее, какой цвет области месячный календарь для извлечения. Список значений см. в разделе `iColor` параметр [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее параметр цвет для указанного фрагмента управления Календарь месяца, в случае успешного выполнения. Эта функция возвращает -1, если операция завершилась неудачей.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 Извлекает `CMonthCalCtrl` объект, связанный с элементом управления выбора даты и времени.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) объекта, или **NULL** в случае неудачи, или если окно не отображается.  
  
### <a name="remarks"></a>Примечания  
 Элементы управления для даты и времени создания дочернего элемента управления Календарь месяца, когда пользователь щелкает стрелку раскрывающегося списка. Если `CMonthCalCtrl` объект больше не нужен, он будет уничтожен, поэтому приложения не должны полагаться на объект, представляющий календарь месяца дочерних управления выбора даты времени хранения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Возвращает шрифт, используемый в настоящее время, Дата и управления Календарь месяца для элемента управления выбора времени.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CFont](../../mfc/reference/cfont-class.md) объекта, или **NULL** в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 `CFont` Объекта, на который указывает возвращаемое значение является временным и удаляются во время следующей обработки простоя.  
  
##  <a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Получает стиль элемента управления calendar month раскрывающийся список, связанный с текущего элемента управления выбора даты и времени.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль элементом управления Календарь месяца раскрывающийся список, который представляет собой битовую комбинацию (или) стилей элемента управления выбора даты и времени. Дополнительные сведения см. в разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) сообщение, которое описано в Windows SDK.  
  
##  <a name="getrange"></a>CDateTimeCtrl::GetRange  
 Извлекает текущий минимальное и максимальное допустимое системное время для элемент выбора даты и времени.  
  
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
 Указатель на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий самое раннее время, допустимое в `CDateTimeCtrl` объекта.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта или `CTime` объект, содержащий самое позднее время, допустимое в `CDateTimeCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `DWORD` значение, содержащее флаги, указывающие, какие диапазоны задаются. If  
  
 `return value & GDTR_MAX` == 0  
  
 Второй параметр является допустимым. Аналогично Если  
  
 `return value & GDTR_MIN` == 0  
  
 Первый параметр является допустимым.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767), как описано в Windows SDK. В реализации MFC, можно указать `COleDateTime` или `CTime` их использование.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>CDateTimeCtrl::GetTime  
 Получает текущий выбранный времени из элемент выбора даты и времени и помещает его в указанном `SYSTEMTIME` структуры.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *timeDest*  
 В первой версии ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта, который будет получать сведения о времени системы. Во второй версии ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта, который будет получать сведения о времени системы.  
  
 *pTimeDest*  
 Указатель на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения сведения о времени системы. Не должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой версии ненулевое значение, если время успешно записан `COleDateTime` объект; в противном случае — 0. В версиях второй и третий `DWORD` значением, равным **dwFlag** набор элементов [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) структуры. В разделе **примечания** ниже, в разделе для получения дополнительной информации.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769), как описано в Windows SDK. В реализации MFC **GetTime**, можно использовать `COleDateTime` или `CTime` классы, или же можно использовать `SYSTEMTIME` структуры, чтобы сохранить сведения о времени.  
  
 Возвращаемое значение `DWORD` в версиях второй и третий описано выше, указывает ли элемент управления выбора даты и времени установлено состояние «не date», как указано в [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) член структуры `dwFlags`. Если возвращаемое значение равно **GDT_NONE**, элемент управления присвоено состояние «не date» и использует **DTS_SHOWNONE** стиля. Если возвращаемое значение равно **GDT_VALID**, системное время успешно сохранен в месте назначения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Возвращает идеальный размер элемента управления выбора даты и времени, необходимого для отображения текущей даты или времени.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[выходной] `psize`|Указатель на [размер](http://msdn.microsoft.com/library/windows/desktop/dd145106) структуру, содержащую идеального размера для элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение всегда равно `true`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода извлекается идеального размера для отображения элемента управления выбора даты и времени.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>CDateTimeCtrl::SetFormat  
 Задает отображение элемент выбора даты и времени в соответствии с указанным форматом строка.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Параметры  
 *pstrFormat*  
 Указатель на строку формата нулем, который определяет нужную форму. Установка этого параметра **NULL** сбросит строку формата по умолчанию для текущего стиля элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
> [!NOTE]
>  Ввод данных пользователем не определить, успех или неудачу для этого вызова.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Задает цвет для данной части календарь месяца в элементе управления выбора даты и времени.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Параметры  
 `iColor`  
 `int`значение, указывающее, какие области элемента управления Календарь месяца для задания. Это значение может быть одно из следующих значений.  
  
|Значение|Значение|  
|-----------|-------------|  
|MCSC_BACKGROUND|Задайте фоновый цвет, отображаемый между месяцами.|  
|MCSC_MONTHBK|Задайте фоновый цвет, отображаемый в течение месяца.|  
|MCSC_TEXT|Задайте цвет, используемый для отображения текста в течение месяца.|  
|MCSC_TITLEBK|Задайте фоновый цвет, отображаемый в заглавии календаря.|  
|MCSC_TITLETEXT|Задайте цвет, используемый для отображения текста в заглавии календаря.|  
|MCSC_TRAILINGTEXT|Задайте цвет, используемый для отображения заголовка и текста в конце дня. Завершающие и начальные дни-это дни предыдущего и следующего месяца, отображаемые на текущий календарь.|  
  
 `ref`  
 Объект **COLORREF** значение, представляющее цвет, который будет установлен для заданной области месячном календаре.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **COLORREF** значение, представляющее предыдущей настройки цвета для указанного фрагмента управления Календарь месяца, в случае успешного выполнения. В противном случае сообщение возвращает -1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 Задает шрифт, который будет использовать управления Календарь месяца дочерних даты и времени выбора элемента управления.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hFont`  
 Дескриптор шрифта, которая будет задана.  
  
 `bRedraw`  
 Указывает, следует ли при настройке шрифта немедленно перерисовке элемента управления. Установка этого параметра **TRUE** вызывает перерисовку элементом управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Если вы используете этот код, нужно сделать членом вашей `CDialog`-производный класс с именем `m_MonthFont` типа **CFont**.  
  
##  <a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Задает стиль элемента управления calendar month раскрывающийся список, связанный с текущего элемента управления выбора даты и времени.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] `dwStyle`|Новый месяц календаря стиля элемента управления, который представляет собой битовую комбинацию (OR) стили элемента управления Календарь месяца. Дополнительные сведения см. в разделе [стили элемента управления Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие стиль элемента управления calendar month раскрывающегося списка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отправляет [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) сообщение, которое описано в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующем примере кода определяется переменная `m_dateTimeCtrl`, который используется для программного доступа к управления выбора даты и времени. Эта переменная используется в следующем примере.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Пример  
 В следующем примере кода задается управления выбора даты и времени для отображения номера недели, сокращенное названия дней недели и отсутствие сегодня индикатора.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CDateTimeCtrl::SetRange  
 Задает минимальное и максимальное допустимые системное время для элемент выбора даты и времени.  
  
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
 Указатель на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта или [CTime](../../atl-mfc-shared/reference/ctime-class.md) объект, содержащий самое раннее время, допустимое в `CDateTimeCtrl` объекта.  
  
 `pMaxRange`  
 Указатель на `COleDateTime` объекта или `CTime` объект, содержащий самое позднее время, допустимое в `CDateTimeCtrl` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780), как описано в Windows SDK. В реализации MFC, можно указать `COleDateTime` или `CTime` их использование. Если `COleDateTime` объект имеет **NULL** состояние, диапазон будут удалены. Если `CTime` указатель или `COleDateTime` указатель **NULL**, диапазона будут удалены.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="settime"></a>CDateTimeCtrl::SetTime  
 Задает время в элемент выбора даты и времени.  
  
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
 Эта функция-член реализует поведение сообщения Win32 [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782), как описано в Windows SDK. В реализации MFC **SetTime**, можно использовать `COleDateTime` или `CTime` классы, или же можно использовать `SYSTEMTIME` структуры, чтобы задать сведения о времени.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Образец CMNCTRL1 MFC](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)

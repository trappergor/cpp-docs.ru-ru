---
title: Класс COleDateTimeSpan | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1941984093879ba22921d19580618ce8caa04b38
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="coledatetimespan-class"></a>Класс COleDateTimeSpan
Представляет относительного времени временной интервал.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Создает объект `COleDateTimeSpan`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|Создает строковое представление `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::GetDays](#getdays)|Возвращает день часть области это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetHours](#gethours)|Возвращает часть области этот `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Возвращает минуты часть области это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Это возвращает во второй части диапазона `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Возвращает состояние (действия) это `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Возвращает число дней, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Возвращает количество часов, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает количество минут, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает количество секунд, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Задает значение этого `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTimeSpan` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|||  
|-|-|  
|[оператор +, -](#operator_add_-)|Добавление и вычитание изменить знак для `COleDateTimeSpan` значения.|  
|[оператор +=-=](#operator_add_eq_-_eq)|Сложения и вычитания `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.|  
|[оператор =](#operator_eq)|Копирует `COleDateTimeSpan` значение.|  
|[оператор ==, <, < =](#coledatetimespan_relational_operators)|Сравнивает два `COleDateTimeSpan` значения.|  
|[double-оператор](#operator_double)|Преобразует этот `COleDateTimeSpan` значение **двойные**.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Содержит базовый **двойные** для этого `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::m_status](#m_status)|Содержит состояние данного объекта `COleDateTimeSpan` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDateTimeSpan` не имеет базового класса.  
  
 Объект `COleDateTimeSpan` хранит времени в днях.  
  
 `COleDateTimeSpan` используется с классом дополнительное [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime` Инкапсулирует **даты** тип данных OLE-автоматизации. `COleDateTime` представляет абсолютное время значения. Все `COleDateTime` включают вычисления `COleDateTimeSpan` значения. Связь между этими классами является аналогом связь между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>  Реляционные операторы COleDateTimeSpan  
 Операторы сравнения.  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dateSpan*  
 Сравниваемый шаблон `COleDateTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эти операторы сравнения двух значений даты или интервал времени и возвращают **true** Если условие имеет значение true; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  ATLASSERT возникнет в том случае, если один из операндов является недопустимым.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan  
 Создает объект `COleDateTimeSpan`.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dblSpanSrc`  
 Число дней, чтобы скопировать в новый `COleDateTimeSpan` объекта.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Указать значения дней недели и времени копируются в новый `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создавать новые `COleDateTimeSpan` объекты, инициализированные до указанного значения. Краткое описание каждого из этих конструкторов выглядит следующим образом:  
  
- **(COleDateTimeSpan)** создает `COleDateTimeSpan` объект инициализируется значением 0.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** создает `COleDateTimeSpan` объекта из значения с плавающей запятой.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  Создает `COleDateTimeSpan` инициализированный для числовых значений, указанного объекта.  
  
 Состояние нового `COleDateTimeSpan` объекта имеет значение на допустимое.  
  
 Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>  COleDateTimeSpan::Format  
 Создает строковое представление `COleDateTimeSpan` объекта.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Коды, предшествует процента форматирования ( `%`) выполните вход, заменен соответствующим `COleDateTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для **формат** , перечислены ниже:  
  
- **%H** часов в текущий день  
  
- **%M** минут в течение текущего часа  
  
- **%S** секунд в текущую минуту  
  
- **%%** Знак процента  
  
 Четыре коды формата, перечисленные выше — это только коды, которые будет принимать формата.  
  
-  
  
 `nID`  
 Идентификатор ресурса для управления форматом строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащее форматированное значение интервал даты/времени.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эти функции для создания отформатированное представление значения интервал времени. Если это состояние `COleDateTimeSpan` объект имеет значение null, возвращается пустая строка. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс **IDS_INVALID_DATETIMESPAN**.  
  
 Краткое описание формы для этой функции выглядит следующим образом:  
  
 **Формат (** `pFormat` **)**  
 Эта форма форматирует значение, используя строку форматирования, содержащий специальные коды форматирования, которым предшествует знак процента (%), как и в `printf`. Строка формата передается как параметр функции.  
  
 **Формат (** `nID` **)**  
 Эта форма форматирует значение, используя строку форматирования, содержащий специальные коды форматирования, которым предшествует знак процента (%), как и в `printf`. Строка форматирования — это ресурс. Этот строковый ресурс идентификатор передается в качестве параметра.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>  COleDateTimeSpan::GetDays  
 Извлекает день часть это значение интервал даты/времени.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть дня это значение интервал даты/времени.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из этой функции диапазоне приблизительно - 3,615,000 и 3,615,000.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>  COleDateTimeSpan::GetHours  
 Извлекает час часть это значение интервал даты/времени.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часы часть это значение интервал даты/времени.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого функция диапазона от - 23 до 23.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes  
 Возвращает значение минут типа этого значения интервал даты/времени.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть минут это значение интервал даты/времени.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого функция диапазона от - 59 до 59.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds  
 Извлекает во второй части это значение интервал даты/времени.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть секунд в это значение интервал даты/времени.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого функция диапазона от - 59 до 59.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus  
 Возвращает состояние (действия) это `COleDateTimeSpan` объекта.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние данного объекта `COleDateTimeSpan` значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется **DateTimeSpanStatus** перечисляемый тип, который определен в `COleDateTimeSpan` класса.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает этим `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает этим `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает этим `COleDateTimeSpan` объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTimeSpan` недопустимый объект в следующих случаях:  
  
-   Если этот объект в результате переполнения или потери значимости во время операции присваивания арифметические, а именно, `+=` или `-=`.  
  
-   Если к этому объекту было присвоено недопустимое значение.  
  
-   Если состояние этого объекта явно установленного на недопустимый с помощью `SetStatus`.  
  
 Дополнительные сведения об операциях, которые может установить состояние недопустимый см. в разделе [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays  
 Возвращает значение, это значение дату или интервал времени в днях.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение дату или интервал времени, в днях. Несмотря на то, что эта функция является прототипом, чтобы возвращать значение типа double, он всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого диапазона функции между приблизительно - 3.65e6 и 3.65e6.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours  
 Извлекает этот интервал даты/времени значение, выраженное в часах.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение дату или интервал времени, в часах. Несмотря на то, что эта функция является прототипом, чтобы возвращать значение типа double, он всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого диапазона функции между приблизительно - 8.77e7 и 8.77e7.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes  
 Извлекает этот интервал даты/времени значение, выраженное в минутах.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот интервал даты/времени значение, выраженное в минутах. Несмотря на то, что эта функция является прототипом, чтобы возвращать значение типа double, он всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этого диапазона функции между приблизительно - 5.26e9 и 5.26e9.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds  
 Извлекает этот интервал даты/времени значение, выраженное в секундах.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение дату или интервал времени, выраженный в секундах. Несмотря на то, что эта функция является прототипом, чтобы возвращать значение типа double, он всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этой функции в диапазоне между приблизительно - 3.16e11 для 3.16e11.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetTotalDays](#gettotaldays).  
  
##  <a name="m_span"></a>  COleDateTimeSpan::m_span  
 Базовый **двойные** значение для данного `COleDateTime` объекта.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Примечания  
 Это значение представляет дату или интервал времени в днях.  
  
> [!CAUTION]
>  Изменение значения в **двойные** элемента данных приведет к изменению значения этого `COleDateTimeSpan` объекта. Это не приводит к изменению состояния этого `COleDateTimeSpan` объекта.  
  
##  <a name="m_status"></a>  COleDateTimeSpan::m_status  
 Тип для этого элемента данных является перечисляемым типом **DateTimeSpanStatus**, которая определена в `COleDateTimeSpan` класса.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Примечания  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает этим `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает этим `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает этим `COleDateTimeSpan` объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTimeSpan` недопустимый объект в следующих случаях:  
  
-   Если этот объект в результате переполнения или потери значимости во время операции присваивания арифметические, а именно, `+=` или `-=`.  
  
-   Если к этому объекту было присвоено недопустимое значение.  
  
-   Если состояние этого объекта явно установленного на недопустимый с помощью [SetStatus](#setstatus).  
  
 Дополнительные сведения об операциях, которые может установить состояние недопустимый см. в разделе [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). В разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания этого элемента данных.  
  
 Дополнительные сведения о граничные значения для `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =  
 Копирует `COleDateTimeSpan` значение.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор назначения перегруженных копирует исходное значение интервал даты/времени в этот `COleDateTimeSpan` объекта.  
  
##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +, -  
 Добавление и вычитание изменить знак для `COleDateTimeSpan` значения.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Первые два операторы позволяют добавлять и вычитать значения даты или интервал времени. Третий позволяет изменить знак значения интервал даты/времени.  
  
 Если любой из операндов имеет значение null, итоговое состояние `COleDateTimeSpan` имеет значение null.  
  
 Если один из операндов является недопустимым, и другой не равно null, итоговое состояние `COleDateTimeSpan` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator +=-=  
 Сложения и вычитания `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют добавлять и вычитать интервал даты/времени значения из этого `COleDateTimeSpan` объекта. Если любой из операндов имеет значение null, итоговое состояние `COleDateTimeSpan` имеет значение null.  
  
 Если один из операндов является недопустимым, и другой не равно null, итоговое состояние `COleDateTimeSpan` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>  Двойные COleDateTimeSpan::operator  
 Преобразует этот `COleDateTimeSpan` значение **двойные**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает значение этого аргумента `COleDateTimeSpan` значение с плавающей запятой количество дней.  
  
##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan  
 Задает значение этого значения интервал даты/времени.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Указать значения диапазоне дат и интервал времени, необходимо скопировать в это `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Для функций, которые запроса значения `COleDateTimeSpan` см. в разделе следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus  
 Задает состояние (действия) это `COleDateTimeSpan` объекта.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Значения состояния для данного `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется **DateTimeSpanStatus** перечисляемый тип, который определен в `COleDateTimeSpan` класса.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает этим `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает этим `COleDateTimeSpan` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает этим `COleDateTimeSpan` объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
    > [!CAUTION]
    >  Эта функция предназначена для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для присвоения состоянию `null` или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTimeSpan](#setdatetimespan) задать состояние объекта на основании исходного значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)



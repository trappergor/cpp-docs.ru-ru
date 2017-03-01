---
title: "Класс COleDateTimeSpan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.COleDateTimeSpan
- COleDateTimeSpan
- ATL::COleDateTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4091ca2c766d56d8398119413778af0a0405b8ab
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetimespan-class"></a>Класс COleDateTimeSpan
Представляет относительного времени за период времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Создает объект `COleDateTimeSpan`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|Создает строковое представление `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::GetDays](#getdays)|Возвращает день диапазона это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetHours](#gethours)|Возвращает часть диапазона `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Возвращает минуты диапазона это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Возвращает часть секунд в диапазоне `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Возвращает состояние (действия) это `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Возвращает количество дней, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Возвращает количество часов, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает количество минут, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает количество секунд, это `COleDateTimeSpan` представляет.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Задает значение этого `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTimeSpan` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|||  
|-|-|  
|[оператор +, -](#operator_add_-)|Добавление и вычитание изменить знак для `COleDateTimeSpan` значения.|  
|[оператор +=-=](#operator_add_eq_-_eq)|Добавление и вычитание `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.|  
|[оператор =](#operator_eq)|Копирует `COleDateTimeSpan` значение.|  
|[оператор ==,<,></,><>](#coledatetimespan_relational_operators)|Сравнить два `COleDateTimeSpan` значения.|  
|[double-оператор](#operator_double)|Преобразует этот `COleDateTimeSpan` значение **двойные**.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Содержит базовый **двойные** для этого `COleDateTimeSpan` объекта.|  
|[COleDateTimeSpan::m_status](#m_status)|Содержит состояние данного объекта `COleDateTimeSpan` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDateTimeSpan`не имеет базового класса.  
  
 Объект `COleDateTimeSpan` хранит времени в днях.  
  
 `COleDateTimeSpan`используется вместе с его вспомогательный класс [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`Инкапсулирует **даты** тип данных OLE-автоматизации. `COleDateTime`Представляет значения абсолютного времени. Все `COleDateTime` вычислений включают `COleDateTimeSpan` значения. Связь между этими классами аналогична связь между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классы, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComTime.h  
  
##  <a name="a-namecoledatetimespanrelationaloperatorsa--coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>Реляционные операторы COleDateTimeSpan  
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
 Эти операторы сравнивают два значения интервала даты и времени и возвращают **true** Если условие имеет значение true; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  ATLASSERT возникнет в том случае, если один из операндов является недопустимым.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#25;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#26;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="a-namecoledatetimespana--coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 Создает объект `COleDateTimeSpan`.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dblSpanSrc`  
 Число дней должно быть скопировано в новый `COleDateTimeSpan` объекта.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Значения дней недели и времени, необходимо скопировать в новый `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создать `COleDateTimeSpan` объекты, инициализированные в указанное значение. Краткое описание каждого из этих конструкторов выглядит следующим образом:  
  
- **(COleDateTimeSpan)** создает `COleDateTimeSpan` объект инициализируется значением 0.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** создает `COleDateTimeSpan` объекта из значения с плавающей запятой.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** создает `COleDateTimeSpan` инициализированный для числовых значений, указанного объекта.  
  
 Состояние нового `COleDateTimeSpan` объекта имеет значение на допустимое.  
  
 Дополнительные сведения о границы `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#14;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="a-nameformata--coledatetimespanformat"></a><a name="format"></a>COleDateTimeSpan::Format  
 Создает строковое представление `COleDateTimeSpan` объекта.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Форматирование кодов, ставится в процентах ( `%`) выполните вход, заменен соответствующим `COleDateTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для **формат** перечислены ниже:  
  
- **%H** часов в текущий день  
  
- **Один** минут в течение текущего часа  
  
- **%S** секунды в текущей минуте  
  
- **%%**Знак процента  
  
 Четыре коды формата, перечисленные выше — это только коды, которые будет принимать формата.  
  
-  
  
 `nID`  
 Идентификатор ресурса для управления форматом строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащая отформатированное значение интервала даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эти функции, чтобы создать форматированное представление значение интервала времени. Если это состояние `COleDateTimeSpan` объект имеет значение null, возвращается пустая строка. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс **IDS_INVALID_DATETIMESPAN**.  
  
 Краткое описание формы для этой функции выглядит следующим образом:  
  
 **Format(** `pFormat` **)**  
 Эта форма форматирует значение с помощью строки формата, содержащего специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка формата передается как параметр функции.  
  
 **Format(** `nID` **)**  
 Эта форма форматирует значение с помощью строки формата, содержащего специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка форматирования является ресурсом. Идентификатор этого ресурса строка передается как параметр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#15;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="a-namegetdaysa--coledatetimespangetdays"></a><a name="getdays"></a>COleDateTimeSpan::GetDays  
 Возвращает день часть это значение интервала даты и времени.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть дня это значение интервала даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Возврат значений из данного диапазона функции между приблизительно — 3,615,000 и 3,615,000.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities №&16;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="a-namegethoursa--coledatetimespangethours"></a><a name="gethours"></a>COleDateTimeSpan::GetHours  
 Возвращает час часть это значение интервала даты и времени.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть часов это значение интервала даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из функции диапазона от-23 до 23.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&17;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="a-namegetminutesa--coledatetimespangetminutes"></a><a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 Возвращает минуты часть это значение интервала даты и времени.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть минут это значение интервала даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из данного диапазона функции между — 59 до 59.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&18;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="a-namegetsecondsa--coledatetimespangetseconds"></a><a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 Извлекает во второй части этого значения интервала даты и времени.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Часть секунд это значение интервала даты и времени.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из данного диапазона функции между — 59 до 59.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&19;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="a-namegetstatusa--coledatetimespangetstatus"></a><a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 Возвращает состояние (действия) это `COleDateTimeSpan` объекта.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние данного объекта `COleDateTimeSpan` значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется **DateTimeSpanStatus** перечислимый тип, который определен в `COleDateTimeSpan` класса.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает это `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает это `COleDateTimeSpan` недопустимый объект; то есть, его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает это `COleDateTimeSpan` объект имеет значение null, то есть, что для этого объекта не указано никакого значения. (Значение «NULL» в смысле базы данных «предложений having не значение» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTimeSpan` недопустимый объект в следующих случаях:  
  
-   Если этот объект опыт переполнения или потери значимости во время назначения арифметические операции, а именно, `+=` или `-=`.  
  
-   Если недопустимое значение был назначен этот объект.  
  
-   Если состояние этого объекта было задано явно недопустимого с помощью `SetStatus`.  
  
 Дополнительные сведения об операциях, которые может задать состояние недопустимый см [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Дополнительные сведения о границы `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-namegettotaldaysa--coledatetimespangettotaldays"></a><a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 Извлекает значение интервала даты и времени в днях.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение интервала даты и времени, выраженное в днях. Несмотря на то, что эта функция является прототипом для возврата типа double, всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из данного диапазона функции между приблизительно — 3.65e6 и 3.65e6.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&20;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="a-namegettotalhoursa--coledatetimespangettotalhours"></a><a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 Извлекает значение интервала даты и времени в часах.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение интервала даты и времени, выраженное в часах. Несмотря на то, что эта функция является прототипом для возврата типа double, всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из данного диапазона функции между приблизительно — 8.77e7 и 8.77e7.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 В примере показано [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalminutesa--coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 Получает это значение интервала даты и времени, выраженный в минутах.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение интервала даты и времени, выраженный в минутах. Несмотря на то, что эта функция является прототипом для возврата типа double, всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые значения из данного диапазона функции между приблизительно — 5.26e9 и 5.26e9.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 В примере показано [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalsecondsa--coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 Извлекает значение интервала даты и времени в секундах.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Это значение интервала даты и времени, выраженный в секундах. Несмотря на то, что эта функция является прототипом для возврата типа double, всегда будет возвращать целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 Значения, возвращаемые из этой функции в диапазоне между приблизительно — 3.16e11-3.16e11.  
  
 Для других функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Пример  
 В примере показано [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namemspana--coledatetimespanmspan"></a><a name="m_span"></a>COleDateTimeSpan::m_span  
 Базовый **двойные** значение для этой `COleDateTime` объекта.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Примечания  
 Это значение представляет дату или интервал времени в днях.  
  
> [!CAUTION]
>  Изменение значения в **двойные** член данных приведет к изменению значения этого `COleDateTimeSpan` объекта. Не изменяет состояние данного объекта `COleDateTimeSpan` объекта.  
  
##  <a name="a-namemstatusa--coledatetimespanmstatus"></a><a name="m_status"></a>COleDateTimeSpan::m_status  
 Тип для этого элемента данных — перечислимый тип **DateTimeSpanStatus**, которая определена в `COleDateTimeSpan` класса.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Примечания  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает это `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает это `COleDateTimeSpan` недопустимый объект; то есть, его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает это `COleDateTimeSpan` объект имеет значение null, то есть, что для этого объекта не указано никакого значения. (Значение «NULL» в смысле базы данных «предложений having не значение» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTimeSpan` недопустимый объект в следующих случаях:  
  
-   Если этот объект опыт переполнения или потери значимости во время назначения арифметические операции, а именно, `+=` или `-=`.  
  
-   Если недопустимое значение был назначен этот объект.  
  
-   Если состояние этого объекта было задано явно недопустимого с помощью [SetStatus](#setstatus).  
  
 Дополнительные сведения об операциях, которые может задать состояние недопустимый см [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) и [COleDateTimeSpan::operator +=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать встроенные функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). В разделе `SetStatus` для дальнейшего предостережения о явном задании этого элемента данных.  
  
 Дополнительные сведения о границы `COleDateTimeSpan` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-nameoperatoreqa--coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDateTimeSpan::operator =  
 Копирует `COleDateTimeSpan` значение.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор назначения перегруженных копирует исходное значение интервала даты и времени в это `COleDateTimeSpan` объекта.  
  
##  <a name="a-nameoperatoradd-a--coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDateTimeSpan::operator +, -  
 Добавление и вычитание изменить знак для `COleDateTimeSpan` значения.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Первые два оператора позволяют добавлять и вычитать значения интервала даты и времени. Третий позволяет изменить знак значения интервала даты и времени.  
  
 Если любой из операндов имеет значение null, состояние конечного `COleDateTimeSpan` имеет значение null.  
  
 Если любой из операндов недопустимо и другой не равно null, состояние результата `COleDateTimeSpan` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#23;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator +=-=  
 Добавление и вычитание `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значение.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют добавлять и вычитать значения интервала даты и времени из этого `COleDateTimeSpan` объекта. Если любой из операндов имеет значение null, состояние конечного `COleDateTimeSpan` имеет значение null.  
  
 Если любой из операндов недопустимо и другой не равно null, состояние результата `COleDateTimeSpan` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#24;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="a-nameoperatordoublea--coledatetimespanoperator-double"></a><a name="operator_double"></a>Двойные COleDateTimeSpan::operator  
 Преобразует этот `COleDateTimeSpan` значение **двойные**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает значение этой `COleDateTimeSpan` значение с плавающей запятой количество дней.  
  
##  <a name="a-namesetdatetimespana--coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 Задает значение этого интервала даты и времени.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Указать значения копируются в этом диапазоне дат и времени `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Для функций, которые запроса значения `COleDateTimeSpan` объекта, см. следующие функции-члены:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#21;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="a-namesetstatusa--coledatetimespansetstatus"></a><a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 Задает состояние (действия) это `COleDateTimeSpan` объекта.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Новое значение для этого состояния `COleDateTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется **DateTimeSpanStatus** перечислимый тип, который определен в `COleDateTimeSpan` класса.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleDateTimeSpan::valid** указывает это `COleDateTimeSpan` объект является допустимым.  
  
- **COleDateTimeSpan::invalid** указывает это `COleDateTimeSpan` недопустимый объект; то есть, его значение может быть неправильным.  
  
- **COleDateTimeSpan::null** указывает это `COleDateTimeSpan` объект имеет значение null, то есть, что для этого объекта не указано никакого значения. (Значение «NULL» в смысле базы данных «предложений having не значение» в отличие от C++ **NULL**.)  
  
    > [!CAUTION]
    >  Эта функция предназначена для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для присвоения состоянию `null` или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTimeSpan](#setdatetimespan) задать состояние объекта на основании исходного значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#22;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




---
title: Класс COleDateTime | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ac939714eff9473397cbe50075f3082f38cdf23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="coledatetime-class"></a>Класс COleDateTime
Инкапсулирует `DATE` тип данных, используемый в OLE-автоматизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Создает объект `COleDateTime`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Создает строковое представление `COleDateTime` объекта.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **DBTIMESTAMP** структуры данных.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Этот метод вызывается для получения времени в `COleDateTime` объекта в виде [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры данных.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Этот метод вызывается для получения времени в `COleDateTime` как **UDATE** структуры данных.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Создает `COleDateTime` объект, который представляет текущее время (статическая функция-член).|  
|[COleDateTime::GetDay](#getday)|Возвращает день это `COleDateTime` представляет объект (1-31).|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, это `COleDateTime` представляет (воскресенье = 1).|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Возвращает день года, это `COleDateTime` представляет (1 января = 1).|  
|[COleDateTime::GetHour](#gethour)|Возвращает час, это `COleDateTime` представляет (0 - 23).|  
|[COleDateTime::GetMinute](#getminute)|Возвращается значение минут это `COleDateTime` представляет (0 - 59).|  
|[COleDateTime::GetMonth](#getmonth)|Возвращает месяц, это `COleDateTime` представляет объект (1-12).|  
|[COleDateTime::GetSecond](#getsecond)|Возвращает второй этот `COleDateTime` представляет (0 - 59).|  
|[COleDateTime::GetStatus](#getstatus)|Возвращает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::GetYear](#getyear)|Возвращает год, это `COleDateTime` представляет.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Считывает значение даты и времени из строки и задает значение `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Задает значение этого `COleDateTime` объект с указанным значением только дата.|  
|[COleDateTime::SetDateTime](#setdatetime)|Задает значение этого `COleDateTime` значение указанной даты времени.|  
|[COleDateTime::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::SetTime](#settime)|Задает значение этого `COleDateTime` объект с указанным значением только со временем.|  
  
### <a name="public-operators"></a>Открытые операторы  

|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::operator == COleDateTime::operator < и т. д.](#coledatetime_relational_operators)|Сравнивает два `COleDateTime` значения.|  
|[COleDateTime::operator + COleDateTime::operator-](#operator_add_-)|Сложения и вычитания `COleDateTime` значения.|  
|[COleDateTime::operator +=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Сложения и вычитания `COleDateTime` значение из этого `COleDateTime` объекта.|  
|[COleDateTime::operator =](#operator_eq)|Копирует `COleDateTime` значение.|  
|[COleDateTime::operator даты, дата COleDateTime::operator *](#operator_date)|Преобразует `COleDateTime` значение в `DATE` или `DATE*`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Содержит базовый **даты** для этого `COleDateTime` объекта.|  
|[COleDateTime::m_status](#m_status)|Содержит состояние данного объекта `COleDateTime` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDateTime` не имеет базового класса.  
  
 Это один из возможных типов для [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) тип данных OLE-автоматизации. Объект `COleDateTime` значение представляет абсолютное значение даты и времени.  
  
 `DATE` Тип реализован как значение с плавающей запятой. Дни отсчитываются от 30 декабря 1899 г., в полночь. Ниже приведены некоторые даты и связанные с ними значения:  
  
|Дата|Значение|  
|----------|-----------|  
|Полночь 29 декабря 1899 г.,|-1.0|  
|29 декабря 1899 г., по 6|-1.25|  
|Полночь 30 декабря 1899 г.,|0,0|  
|Полночь 31 декабря 1899 г.,|1.0|  
|1 января 1900 г., 6: 00.|2.25|  
  
> [!CAUTION]
>  Обратите внимание, в приведенной выше таблице, несмотря на то, что значения дня становиться отрицательными до полуночи 30 декабря 1899 г., время дня значений нет. Например 6:00 AM всегда имеет дробные значения от 0,25 независимо от того, целое число, представляющее день (после 30 декабря 1899 г.) минус (до 30 декабря 1899 г.). Это означает, что простым сравнением плавающей точки ошибочно отсортировать `COleDateTime` представляющий 6:00:00 12/29/1899 г как **позже** чем представляющий 07:00:00 в тот же день.  
  
 `COleDateTime` Класс обрабатывает даты с 1 января 100 до 31 декабря 9999 года. `COleDateTime` Класс с помощью григорианского календаря; он не поддерживает юлианский даты. `COleDateTime` игнорирует летнего времени. (См. [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Можно использовать `%y` формата для получения только для дат, начиная с 1900 года двумя цифрами. Если вы используете `%y` формат до даты 1900, код создает ошибку ASSERT.  
  
 Этот тип также используется для представления значений только дату или только со временем. По соглашению Дата 0 (30 декабря 1899 г.) используется для значений только во время и время 00:00 (полночь) используется для значения, доступные только для даты.  
  
 При создании `COleDateTime` с использованием даты не более 100 дата является правильным, но последующие вызовы `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, и `GetSecond` ошибкой и возвращают -1. Ранее можно использовать заданные двумя цифрами, но даты должны быть 100 или больше в MFC версии 4.2 и более поздних версий.  
  
 Чтобы избежать проблем, укажите дату из четырех цифр. Пример:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Основные арифметические операции для `COleDateTime` значения используйте класс дополнительное [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan` значения определяют интервал времени. Связь между этими классами подобное между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>  Реляционные операторы COleDateTime  
 Операторы сравнения.  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `date`  
 **COleDateTime** объект для сравнения.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  ATLASSERT возникнет в том случае, если любой из двух операндов недопустимо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Пример  
 Операторы **>=**, **\< =**, **>**, и **<**, проверяет, если `COleDateTime` объекта установлено в значение null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>  COleDateTime::COleDateTime  
 Создает объект `COleDateTime`.  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dateSrc`  
 Существующий `COleDateTime` скопировать в новый объект `COleDateTime` объекта.  
  
 *varSrc*  
 Существующий **VARIANT** структура данных (возможно `COleVariant` объекта) должно быть преобразовано в значение даты и времени ( `VT_DATE`) и скопировать в новый `COleDateTime` объекта.  
  
 `dtSrc`  
 Даты и времени ( **даты**) значения, которое копируется в новый `COleDateTime` объекта.  
  
 `timeSrc`  
 Объект `time_t` или **__time64_t** значение преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 *systimeSrc*  
 Объект `SYSTEMTIME` структура преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 `filetimeSrc`  
 Объект `FILETIME` структура преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта. Обратите внимание, что `FILETIME` использует общего скоординированного времени (UTC), если передать местное время в структуре, результаты могут оказаться неверными. В разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в Windows SDK для получения дополнительной информации.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Указать значения даты и времени, который необходимо скопировать в новый `COleDateTime` объекта.  
  
 `wDosDate`, `wDosTime`  
 Значения даты и времени MS-DOS преобразовывается в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 `dbts`  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структуру, содержащую текущее местное время.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создавать новые `COleDateTime` объекты, инициализированные до указанного значения. В следующей таблице показаны допустимые диапазоны для каждого компонента даты и времени:  
  
|Компонент даты и времени|Допустимый диапазон значений|  
|--------------------------|-----------------|  
|год|100 - 9999|  
|месяц|0 - 12|  
|дн|0 - 31|  
|Час|0 - 23|  
|Минуты|0 - 59|  
|second|0 - 59|  
  
 Обратите внимание, что зависит от фактического верхнюю границу компонент дня зависимости от компонентов месяц и год. Дополнительные сведения см. в разделе **SetDate** или `SetDateTime` функции-члены.  
  
 Вот краткое описание каждого конструктора:  
  
- `COleDateTime(` **)** Создает `COleDateTime` объект инициализируется значением 0 (полночь 30 декабря 1899 г.).  
  
- `COleDateTime(` `dateSrc` **)** Создает `COleDateTime` объекта из существующего `COleDateTime` объекта.  
  
- `COleDateTime(` *varSrc* **)** создает `COleDateTime` объекта. Пытается преобразовать `VARIANT` структуры или [COleVariant](../../mfc/reference/colevariant-class.md) объекта даты и времени ( `VT_DATE`) значение. Если преобразование прошло успешно, преобразованное значение копируется в новый `COleDateTime` объекта. Если это не так, значение `COleDateTime` , присваивается значение 0 (полночь 30 декабря 1899 г.) и его состояние недопустимой.  
  
- `COleDateTime(` `dtSrc` **)** Создает `COleDateTime` объекта из **даты** значение.  
  
- `COleDateTime(` `timeSrc` **)** Создает `COleDateTime` объекта из `time_t` значение.  
  
- `COleDateTime(` *systimeSrc* **)** создает `COleDateTime` объекта из `SYSTEMTIME` значение.  
  
- `COleDateTime(` `filetimeSrc` **)** Создает `COleDateTime` объекта из `FILETIME` значение. . Обратите внимание, что `FILETIME` использует общего скоординированного времени (UTC), если передать местное время в структуре, результаты могут оказаться неверными. В разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в Windows SDK для получения дополнительной информации.  
  
- `COleDateTime(` `nYear``nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Создает `COleDateTime` объект из указанного числовые значения.  
  
- `COleDateTime(` `wDosDate``wDosTime` **)** Создает `COleDateTime` объект из указанного значения даты и времени MS-DOS.  
  
 Дополнительные сведения о `time_t` тип данных, в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) функционировать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуры в Windows SDK.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  Конструктор с помощью **DBTIMESTAMP** параметр доступен, только если включено OLEDB.h.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>  COleDateTime::Format  
 Создает отформатированное представление значения даты и времени.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Указывает один из следующих флагов языкового стандарта:  
  
- `LOCALE_NOUSEROVERRIDE` Используйте параметры языкового стандарта системы по умолчанию, вместо пользовательских параметров.  
  
- `VAR_TIMEVALUEONLY` Игнорировать часть даты во время синтаксического анализа.  
  
- `VAR_DATEVALUEONLY` Пропускать части времени во время синтаксического анализа.  
  
 `lcid`  
 Указывает код языка, используют для преобразования. Дополнительные сведения об идентификаторах языков см. в разделе [идентификаторы языка](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 `lpszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Каждый форматирование кода, предшествует процента ( `%`) выполните вход, заменен соответствующим `COleDateTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. В описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) для получения дополнительной информации. Значение и значение коды форматирования для `Format` являются:  
  
- `%H` Часы в текущий день  
  
- `%M` Минут в течение текущего часа  
  
- `%S` В текущей минуте секунды  
  
- `%%` Знак процента  
  
 `nFormatID`  
 Идентификатор ресурса для управления форматом строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащее значение даты и времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Если это состояние `COleDateTime` объект имеет значение null, возвращается пустая строка. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс `ATL_IDS_DATETIME_INVALID`.  
  
 Краткое описание трех форм для этой функции выглядит следующим образом:  
  
 `Format`( `dwFlags`, `lcid`)  
 Эта форма форматирует значение с помощью спецификации языка (локаль идентификаторы) для даты и времени. С параметрами по умолчанию, эта форма будет печататься дату и время, пока — 0 (полночь) времени, в этом случае оно печатается только даты, или часть даты является 0 (30 декабря 1899 г.), в этом случае оно печатается только время. Если значение даты и времени равно 0 (30 декабря 1899 г., полночь), эта форма с параметрами по умолчанию будет печататься в полночь.  
  
 `Format`( `lpszFormat`)  
 Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которым предшествует знак процента (%), как и в `printf`. Строка формата передается как параметр функции. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в справочнике библиотеки времени выполнения.  
  
 `Format`( `nFormatID`)  
 Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которым предшествует знак процента (%), как и в `printf`. Строка форматирования — это ресурс. Этот строковый ресурс идентификатор передается в качестве параметра. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в *Справочник по библиотеке времени выполнения*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>  COleDateTime::GetAsDBTIMESTAMP  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **DBTIMESTAMP** структуры данных.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dbts`  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сохраняет полученное время в структуре `dbts`, на которую указана ссылка. **DBTIMESTAMP** данных структуру, инициализированную эта функция будет иметь его **дробь** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>  COleDateTime::GetAsSystemTime  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде `SYSTEMTIME` структуры данных.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *sysTime*  
 Ссылку на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры для получения значения, преобразованные даты и времени из `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения; **false** при сбое преобразования, или если `COleDateTime` объект **NULL** или недопустим.  
  
### <a name="remarks"></a>Примечания  
 `GetAsSystemTime` сохраняет полученное время упоминаемого *sysTime* объекта. `SYSTEMTIME` Данных структуру, инициализированную эта функция будет иметь его **wMilliseconds** член равен нулю.  
  
 В разделе [GetStatus](#getstatus) для Дополнительные сведения о состоянии, которые содержатся в `COleDateTime` объекта.  
  
##  <a name="getasudate"></a>  COleDateTime::GetAsUDATE  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **UDATE** структуры данных.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `udate`  
 Ссылку на **UDATE** структуры для получения значения, преобразованные даты и времени из `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения; **false** при сбое преобразования, или если `COleDateTime` объект **NULL** или недопустим.  
  
### <a name="remarks"></a>Примечания  
 Объект **UDATE** структура представляет дату «распакованы».  
  
##  <a name="getcurrenttime"></a>  COleDateTime::GetCurrentTime  
 Вызовите это статическая функция-член возвращает значение текущей даты и времени.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>  COleDateTime::GetDay  
 Возвращает день месяца, представленный это значение даты и времени.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День месяца, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить день.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 1 до 31.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>  COleDateTime::GetDayOfWeek  
 Возвращает день месяца, представленный это значение даты и времени.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День недели, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить день недели.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемые значения диапазона от 1 до 7, где 1 = воскресенье, 2 = понедельник и т. д.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>  COleDateTime::GetDayOfYear  
 Возвращает день года, представленный это значение даты и времени.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День года, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить день года.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемого значения в диапазоне от 1 до 366, где 1 января = 1.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>  COleDateTime::GetHour  
 Возвращает час, представленный это значение даты и времени.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Час, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить час.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 23.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>  COleDateTime::GetMinute  
 Возвращает минуту, представленный это значение даты и времени.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минуты, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить минуты.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 59.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHour](#gethour).  
  
##  <a name="getmonth"></a>  COleDateTime::GetMonth  
 Возвращает месяца, представленный это значение даты и времени.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Месяца, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить месяца.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 1 до 12.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetDay](#getday).  
  
##  <a name="getsecond"></a>  COleDateTime::GetSecond  
 Возвращает второй, представленный это значение даты и времени.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Второй, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить второй.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 59.  
  
> [!NOTE]
>  `COleDateTime` Класс не поддерживает корректировочных секунд.  
  
 Дополнительные сведения о реализации для `COleDateTime`, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHour](#gethour).  
  
##  <a name="getstatus"></a>  COleDateTime::GetStatus  
 Возвращает состояние (действия) заданного `COleDateTime` объекта.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние данного объекта `COleDateTime` значение. При вызове метода **GetStatus** на `COleDateTime` объект создан со значением по умолчанию, он будет возвращать допустимое. При вызове метода **GetStatus** на `COleDateTime` объект инициализируется с конструктором, имеющим значение null, **GetStatus** вернет значение null. В разделе **примечания** для получения дополнительной информации.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется **DateTimeStatus** перечисляемый тип, который определен в `COleDateTime` класса.  
  
```  
enum DateTimeStatus  
{  
   error = -1,  
   valid = 0,  
   invalid = 1,    // Invalid date (out of range, etc.)  
   null = 2,       // Literally has no value  
};  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- `COleDateTime::error` Указывает, что произошла ошибка при попытке получить часть значения даты и времени.  
  
- **COleDateTime::valid** указывает этим `COleDateTime` объект является допустимым.  
  
- **COleDateTime::invalid** указывает этим `COleDateTime` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleDateTime::null** указывает этим `COleDateTime` объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTime` недопустимый объект в следующих случаях:  
  
-   Если его значение установлено из **VARIANT** или `COleVariant` значение, которое не удалось преобразовать значение даты и времени.  
  
-   Если его значение установлено из `time_t`, `SYSTEMTIME`, или `FILETIME` значение, которое не удалось преобразовать значение допустимые дату и время.  
  
-   Если его значение установлено `SetDateTime` с недопустимые значения параметров.  
  
-   Если этот объект в результате переполнения или потери значимости во время операции присваивания арифметические, а именно, `+=` или `-=`.  
  
-   Если к этому объекту было присвоено недопустимое значение.  
  
-   Если состояние этого объекта явно установленного на недопустимый с помощью `SetStatus`.  
  
 Дополнительные сведения об операциях, которые может присвоить состояние недопустимый см. в разделе следующие функции-члены:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [оператор +, -](#operator_add_-)  
  
- [оператор +=-=](#operator_add_eq_-_eq)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>  COleDateTime::GetYear  
 Возвращает года, это значение даты и времени.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Год, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` , если не удалось получить год.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых значений для возврата от 100 до 9999, включая век.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetDay](#getday).  
  
##  <a name="m_dt"></a>  COleDateTime::m_dt  
 Базовый **даты** структуры для этого `COleDateTime` объекта.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в **даты** измените это значение, это объект, к которому указатель, возвращаемый этой функцией `COleDateTime` объекта. Это не приводит к изменению состояния этого `COleDateTime` объекта.  
  
 Дополнительные сведения о реализации **даты** объектов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="m_status"></a>  COleDateTime::m_status  
 Содержит состояние данного объекта `COleDateTime` объекта.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Примечания  
 Тип этого элемента данных является перечисляемым типом **DateTimeStatus**, которая определена в `COleDateTime` класса. В разделе [COleDateTime::GetStatus](#getstatus) подробные сведения.  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). В разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания этого элемента данных.  
  
##  <a name="operator_eq"></a>  COleDateTime::operator =  
 Копирует `COleDateTime` значение.  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти перегруженных операторах присваивания копирования исходное значение даты и времени в это `COleDateTime` объекта. Краткое описание всех этих перегружать следующим операторы присваивания:  
  
- **оператор = (** `dateSrc` **)** копируется в это значение и состояние операнда `COleDateTime` объекта.  
  
- **оператор = (** *varSrc* **)** Если преобразование [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) значение (или [COleVariant](../../mfc/reference/colevariant-class.md) объекта) (даты и времени `VT_DATE`) является успешной, преобразованное значение копируется в этот `COleDateTime` объекта и его состояние имеет значение на допустимое. Если преобразование не выполнено успешно, значение этого объекта равно нуль (30 декабря 1899 г., полночь) и его состояние недопустимой.  
  
- **оператор = (** `dtSrc` **)** **даты** значение копируется в этот `COleDateTime` объекта и его состояние имеет значение на допустимое.  
  
- **оператор = (** `timeSrc` **)** `time_t` или **__time64_t** преобразуется и скопировать в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта имеет значение допустимым; Если операция завершилась неудачно, он настраивается на недопустимый.  
  
- **оператор = (** *systimeSrc* **)** [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) преобразуется и скопировать в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта имеет значение допустимым; Если операция завершилась неудачно, он настраивается на недопустимый.  
  
- **оператор = (** `udate` **)** **UDATE** преобразуется и скопировать в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта имеет значение допустимым; Если операция завершилась неудачно, он настраивается на недопустимый. Объект **UDATE** структура представляет дату «распакованы». В описании функции [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) для получения дополнительных сведений.  
  
- **оператор = (** `filetimeSrc` **)** [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) преобразуется и скопировать в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта имеет значение допустимым; в противном случае устанавливается недопустимой. `FILETIME` использует общего скоординированного времени (UTC), поэтому, если передать время в формате UTC в структуре, результаты преобразуются в формате UTC в местное время и будет храниться в виде variant времени. Это происходит так же, как в Visual C++ 6.0 и Visual C++ .NET 2003 с пакетом обновления 2. В разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в Windows SDK для получения дополнительной информации.  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) входа в Windows SDK.  
  
 Дополнительные сведения о `time_t` тип данных, в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) функционировать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуры в Windows SDK.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_add_-"></a>  COleDateTime::operator +, -  
 Сложения и вычитания **ColeDateTime** значения.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 `COleDateTime` они представляют абсолютное время. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) представляют относительное время. Первые два операторы позволяют сложения и вычитания `COleDateTimeSpan` значение из `COleDateTime` значение. Третий оператор можно вычесть единицу `COleDateTime` значение из другого выдавала `COleDateTimeSpan` значение.  
  
 Если любой из операндов имеет значение null, итоговое состояние `COleDateTime` имеет значение null.  
  
 Если полученный `COleDateTime` находится за пределами допустимых значений, состояние, `COleDateTime` недопустимое значение.  
  
 Если один из операндов является недопустимым, и другой не равно null, итоговое состояние `COleDateTime` недопустимое значение.  
  
 **+** И **-** операторов проверяет, если `COleDateTime` объекта установлено в значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) в качестве примера.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTime::operator +=-=  
 Сложения и вычитания **ColeDateTime** значение из этого `COleDateTime` объекта.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `COleDateTimeSpan` значение в и из этого `COleDateTime`. Если любой из операндов имеет значение null, итоговое состояние `COleDateTime` имеет значение null.  
  
 Если полученный `COleDateTime` находится за пределами допустимых значений, это состояние `COleDateTime` значение недопустимой.  
  
 Если один из операндов является недопустимым, и другие не равно null, итоговое состояние `COleDateTime` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
 **+=** И **-=** операторов проверяет, если `COleDateTime` объекта установлено в значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) в качестве примера.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_date"></a>  COleDateTime::operator даты  
 Преобразует **ColeDateTime** значение в **даты**.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает **даты** , значение которого копируется из этого объекта `COleDateTime` объекта. Дополнительные сведения о реализации **даты** объектов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 **Даты** оператор будет assert, если `COleDateTime` объекта установлено в значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) в качестве примера.  
  
##  <a name="parsedatetime"></a>  COleDateTime::ParseDateTime  
 Выполняет синтаксический анализ строки для чтения значения даты и времени.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszDate`  
 Указатель на завершающуюся значением null строке, которая является для синтаксического анализа. Дополнительные сведения см. в разделе "Заметки".  
  
 `dwFlags`  
 Указывает флаги для региональных параметров и анализа. Один или несколько из следующих флагов:  
  
- **LOCALE_NOUSEROVERRIDE** использовать параметры языкового стандарта системы по умолчанию, а не пользовательских параметров.  
  
- **VAR_TIMEVALUEONLY** игнорировать часть даты во время синтаксического анализа.  
  
- **VAR_DATEVALUEONLY** игнорировать промежуток времени во время синтаксического анализа.  
  
 `lcid`  
 Указывает код языка, используют для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если строка был успешно преобразован в значение даты и времени, в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Если строка был успешно преобразован в даты и времени значение, значение этого аргумента `COleDateTime` присваивается значение этого значения и его статус на допустимое.  
  
> [!NOTE]
>  Год значения должны находиться в диапазоне от 100 до 9999 г. включительно.  
  
 `lpszDate` Параметр может принимать различные форматы. Например следующие строки содержат форматы допустимые даты и времени:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`  
  
 Обратите внимание, что также влияет на код локали ли формат строки приемлемо для преобразования в значение даты и времени.  
  
 В случае использования **VAR_DATEVALUEONLY**, время имеет значение 0 или в течение времени полуночи. В случае использования **VAR_TIMEVALUEONLY**, дата, имеет значение даты 0, то есть 30 декабря 1899 г.  
  
 Если не удалось преобразовать строку в значение даты и времени или в случае отсутствия численного переполнения состояние данного объекта `COleDateTime` недопустимый объект.  
  
 Дополнительные сведения о границах и реализации для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="setdate"></a>  COleDateTime::SetDate  
 Задает дату `COleDateTime` объекта.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nYear`, `nMonth`, `nDay`  
 Указывает компоненты даты необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение этого аргумента `COleDateTime` объекта было установлено успешно, в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Дата устанавливается указанные значения. Время установлено в момент времени 0, полночь.  
  
 См. следующую таблицу для границ для значений параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
  
 При переполнении числа месяца он преобразуется в правильный день следующего месяца и месяца или года соответствующим образом увеличивается. День нулевое значение указывает последний день предыдущего месяца. Поведение совпадает со значением `SystemTimeToVariantTime`.  
  
 Если значение даты, указанный параметрами не является допустимым, состояние этого объекта имеет значение **COleDateTime::invalid**. Следует использовать [GetStatus](#getstatus) для проверки допустимости **даты** значение и не следует предполагать, что значение [m_dt](#m_dt) , останутся неизменными.  
  
 Ниже приведены некоторые примеры значений даты.  
  
|`nYear`|`nMonth`|`nDay`|Значение|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29 февраля 2000 г.|  
|1776|7|4|4 июля 1776|  
|1925|4|35|35 1925 апреля (Недопустимая дата)|  
|10000|1|1|1 января 10000 (Недопустимая дата)|  
  
 Чтобы установить дату и время, в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>  COleDateTime::SetDateTime  
 Задает дату и время этого `COleDateTime` объекта.  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Указывает компоненты даты и времени, который необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение этого аргумента `COleDateTime` объекта было установлено успешно, в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 См. следующую таблицу для границ для значений параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 При переполнении числа месяца он преобразуется в правильный день следующего месяца и месяца или года соответствующим образом увеличивается. День нулевое значение указывает последний день предыдущего месяца. Происходит так же, как [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450).  
  
 Если значение даты или времени, указанный параметрами является недопустимым, недопустим и значения этого объекта задано состояние этого объекта не изменяется.  
  
 Ниже приведены некоторые примеры значений времени.  
  
|`nHour`|`nMin`|`nSec`|Значение|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Недопустимо|  
|9|60|0|Недопустимо|  
  
 Ниже приведены некоторые примеры значений даты.  
  
|`nYear`|`nMonth`|`nDay`|Значение|  
|-------------|--------------|------------|-----------|  
|1995|4|15|15 апреля 1995 г.|  
|1789|7|14|17 июля 1789|  
|1925|2|30|Недопустимо|  
|10000|1|1|Недопустимо|  
  
 Чтобы настроить только дата, см. [COleDateTime::SetDate](#setdate). Чтобы задать только время, в разделе [COleDateTime::SetTime](#settime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetStatus](#getstatus).  
  
##  <a name="setstatus"></a>  COleDateTime::SetStatus  
 Задает состояние данного объекта `COleDateTime` объекта.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Значения состояния для данного `COleDateTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется **DateTimeStatus** перечисляемый тип, который определен в `COleDateTime` класса. В разделе [COleDateTime::GetStatus](#getstatus) подробные сведения.  
  
> [!CAUTION]
>  Эта функция предназначена для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для присвоения состоянию `null` или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTime](#setdatetime) задать состояние объекта на основании исходного значения.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetStatus](#getstatus).  
  
##  <a name="settime"></a>  COleDateTime::SetTime  
 Задает время `COleDateTime` объекта.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nHour`, `nMin`, `nSec`  
 Указывает компоненты времени необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение этого аргумента `COleDateTime` объекта было установлено успешно, в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Время установлено указанные значения. Дата устанавливается на дату 0, то есть 30 декабря 1899 г.  
  
 См. следующую таблицу для границ для значений параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 Если значение, указанное с помощью параметров является недопустимым, время состояния этого объекта имеет значение недопустимо и значение этого объекта не изменяется.  
  
 Ниже приведены некоторые примеры значений времени.  
  
|`nHour`|`nMin`|`nSec`|Значение|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Недопустимо|  
|9|60|0|Недопустимо|  
  
 Чтобы установить дату и время, в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` см. в разделе следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [SetDate](#setdate).  
  
## <a name="see-also"></a>См. также  
 [Класс COleVariant](../../mfc/reference/colevariant-class.md)   
 [Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)




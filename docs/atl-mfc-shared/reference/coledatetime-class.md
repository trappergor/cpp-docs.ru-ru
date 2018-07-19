---
title: Класс COleDateTime | Документация Майкрософт
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
ms.openlocfilehash: 359a7ff75b2036960d8d8ffd40200f9175ccc21c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960704"
---
# <a name="coledatetime-class"></a>Класс COleDateTime
Инкапсулирует `DATE` тип данных, который используется в OLE-автоматизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Создает объект `COleDateTime`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Создает форматированное строковое представление `COleDateTime` объекта.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Вызовите этот метод для получения времени в `COleDateTime` объекта в виде `DBTIMESTAMP` структуру данных.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Вызовите этот метод для получения времени в `COleDateTime` объекта в виде [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру данных.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Вызовите этот метод для получения времени в `COleDateTime` как `UDATE` структуру данных.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Создает `COleDateTime` объект, представляющий текущее время (статическая функция-член).|  
|[COleDateTime::GetDay](#getday)|Возвращает день, это `COleDateTime` представляет (1-31).|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, это `COleDateTime` (воскресенье = 1) представляет объект.|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Возвращает день года, это `COleDateTime` представляет (1 января = 1) объект.|  
|[COleDateTime::GetHour](#gethour)|Возвращает час, это `COleDateTime` представляет объект (0 - 23).|  
|[COleDateTime::GetMinute](#getminute)|Возвращается значение минут это `COleDateTime` представляет объект (0 - 59).|  
|[COleDateTime::GetMonth](#getmonth)|Возвращает месяц, это `COleDateTime` представляет (1-12).|  
|[COleDateTime::GetSecond](#getsecond)|Возвращает второй `COleDateTime` представляет объект (0 - 59).|  
|[COleDateTime::GetStatus](#getstatus)|Получает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::GetYear](#getyear)|Возвращает значение года это `COleDateTime` представляет объект.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Считывает значение даты и времени из строки и задает значение `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Задает значение данного объекта `COleDateTime` объекта указанное значение только дата.|  
|[COleDateTime::SetDateTime](#setdatetime)|Задает значение данного объекта `COleDateTime` значение указанной даты времени.|  
|[COleDateTime::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::SetTime](#settime)|Задает значение данного объекта `COleDateTime` объекта указанное значение только со временем.|  
  
### <a name="public-operators"></a>Открытые операторы  

|Имя|Описание:|  
|----------|-----------------|  
|[COleDateTime::operator == COleDateTime::operator < и т. д.](#coledatetime_relational_operators)|Сравнение двух `COleDateTime` значения.|  
|[COleDateTime::operator + COleDateTime::operator-](#operator_add_-)|Добавление и вычитание `COleDateTime` значения.|  
|[COleDateTime::operator +=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Добавление и вычитание `COleDateTime` значение из этого `COleDateTime` объекта.|  
|[COleDateTime::operator =](#operator_eq)|Копирует `COleDateTime` значение.|  
|[COleDateTime::operator даты, даты COleDateTime::operator *](#operator_date)|Преобразует `COleDateTime` значение в `DATE` или `DATE*`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Содержит базовый `DATE` для данного `COleDateTime` объекта.|  
|[COleDateTime::m_status](#m_status)|Содержит состояние данного объекта `COleDateTime` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDateTime` не имеет базового класса.  
  
 Это одна из возможных типов для [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) тип данных OLE-автоматизации. Объект `COleDateTime` значение представляет абсолютное значение даты и времени.  
  
 `DATE` Тип реализован как значение с плавающей запятой. Дней в полночь отсчитывается от 30 декабря 1899 г. Ниже приведены некоторые даты и связанных с ними значений:  
  
|Дата|Значение|  
|----------|-----------|  
|Полночь 29 декабря 1899 г.,|-1.0|  
|29 декабря 1899 г., 6 по|-1.25|  
|Полночь 30 декабря 1899 г.,|0,0|  
|Полуночи 31 декабря 1899 г.,|1.0|  
|1 января 1900 г., 6: 00|2.25|  
  
> [!CAUTION]
>  Обратите внимание, в приведенной выше таблице, несмотря на то, что значения дня становиться отрицательными до полуночи 30 декабря 1899 года, время дня значений нет. Например 6:00 AM всегда представляется дробное значение 0,25 независимо от типа целое число, представляющее день положительное (после 30 декабря 1899 г.) или отрицательным (до 30 декабря 1899 г.). Это означает, что простое сравнение с плавающей точкой ошибочно отсортировать `COleDateTime` представляющий 06:00:00 12/29/1899 года как **позже** чем та, представляющий 7:00 в тот же день.  
  
 `COleDateTime` Класс обрабатывает даты с 1 января 100 до 31 декабря 9999 года. `COleDateTime` Класс использует григорианского календаря; он не поддерживает юлианскому дат. `COleDateTime` игнорирует летнего времени. (См. в разделе [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Можно использовать `%y` формат для извлечения только для дат, начиная с 1900 года из двух цифр. Если вы используете `%y` формат до даты 1900, код создает ошибку ASSERT.  
  
 Этот тип также используется для представления значений только дату или только время. По соглашению Дата 0 (30 декабря 1899 г.) используется для значения, доступные только для времени и времени 00:00 (полночь) используется для значения, доступные только для даты.  
  
 При создании `COleDateTime` с использованием даты не более 100 дата является правильным, но последующие вызовы `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, и `GetSecond` ошибкой и возвращают -1. Ранее можно было использовать заданные двумя цифрами, но даты должны быть 100 или больше в MFC версии 4.2 и более поздних версий.  
  
 Чтобы избежать проблем, укажите дату из четырех цифр. Пример:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Основные арифметические операции для `COleDateTime` значений используйте вспомогательный класс [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan` значения определяют интервал времени. Связь между этими классами вида между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классов, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>  Операторы отношения COleDateTime  
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
 *date*  
 Сравниваемый объект `COleDateTime`.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  ATLASSERT возникнет в том случае, если любой из двух операндов является недопустимым.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Пример  
 Операторы **>=**, **\< =**, **>**, и **<**, проверяет Если `COleDateTime` объекта задано значение null.  
  
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
 *dateSrc*  
 Существующий `COleDateTime` объект, который необходимо скопировать в новый `COleDateTime` объекта.  
  
 *varSrc*  
 Существующий `VARIANT` структуры данных (возможно `COleVariant` объекта) преобразовывается в значение даты и времени (VT_DATE) и скопировать в новый `COleDateTime` объекта.  
  
 *dtSrc*  
 Даты и времени (`DATE`) значение для копирования в новый `COleDateTime` объекта.  
  
 *timeSrc*  
 Объект `time_t` или `__time64_t` значение преобразовывается в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 *systimeSrc*  
 Объект `SYSTEMTIME` структуры, которые следует преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 *filetimeSrc*  
 Объект `FILETIME` структуры, которые следует преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объекта. Обратите внимание, что `FILETIME` использует всеобщее скоординированное время (UTC), поэтому если передать местное время в структуре, ваши результаты могут оказаться неправильными. См. в разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в пакете SDK для Windows, Дополнительные сведения.  
  
 *nYear*, *nMonth*, *nDay*, *основе Nчас*, *Nмин.*, *nSec*  
 Указать значения даты и времени, который необходимо скопировать в новый `COleDateTime` объекта.  
  
 *wDosDate*, *wDosTime*  
 Значения даты и времени MS-DOS, которые следует преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 *DBTS*  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структуру, содержащую текущее местное время.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создавать новые `COleDateTime` объекты, инициализированные указанное значение. В следующей таблице показаны допустимые диапазоны для каждого компонента даты и времени:  
  
|Компонент даты и времени|Допустимый диапазон|  
|--------------------------|-----------------|  
|год|100 - 9999|  
|месяц|0 - 12|  
|дн|0 - 31|  
|час|0 - 23|  
|минуту|0 - 59|  
|second|0 - 59|  
  
 Обратите внимание, что зависит от фактического верхнюю границу компонент дня зависимости от компонентов месяц и год. Дополнительные сведения см. в разделе `SetDate` или `SetDateTime` функций-членов.  
  
 Вот краткое описание каждого конструктора:  
  
- `COleDateTime(` **)** Создает `COleDateTime` объект инициализируется значением 0 (полночь 30 декабря 1899 года).  
  
- `COleDateTime(` `dateSrc` **)** Создает `COleDateTime` из существующего `COleDateTime` объекта.  
  
- `COleDateTime(` *varSrc* **)** создает `COleDateTime` объекта. Пытается преобразовать `VARIANT` структуры или [COleVariant](../../mfc/reference/colevariant-class.md) объекта даты и времени ( `VT_DATE`) значение. Если это преобразование выполнено успешно, преобразованное значение копируется в новый `COleDateTime` объекта. Если это не так, значение `COleDateTime` объект имеет значение 0 (полночь 30 декабря 1899 г.) и его состояние на недопустимый.  
  
- `COleDateTime(` `dtSrc` **)** Создает `COleDateTime` объекта из `DATE` значение.  
  
- `COleDateTime(` `timeSrc` **)** Создает `COleDateTime` объекта из `time_t` значение.  
  
- `COleDateTime(` *systimeSrc* **)** создает `COleDateTime` объекта из `SYSTEMTIME` значение.  
  
- `COleDateTime(` `filetimeSrc` **)** Создает `COleDateTime` объекта из `FILETIME` значение. . Обратите внимание, что `FILETIME` использует всеобщее скоординированное время (UTC), поэтому если передать местное время в структуре, ваши результаты могут оказаться неправильными. См. в разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в пакете SDK для Windows, Дополнительные сведения.  
  
- `COleDateTime(` `nYear``nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Создает `COleDateTime` объект из указанного числовые значения.  
  
- `COleDateTime(` `wDosDate``wDosTime` **)** Создает `COleDateTime` объект из указанного значения даты и времени MS-DOS.  
  
 Дополнительные сведения о `time_t` тип данных, см. в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) работать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структур в пакете Windows SDK.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  В конструктор с помощью `DBTIMESTAMP` параметр доступен только в случае, если включен OLEDB.h.  
  
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
 *dwFlags*  
 Указывает один из следующих флагов языкового стандарта:  
  
- LOCALE_NOUSEROVERRIDE системные настройки языкового стандарта по умолчанию, используйте вместо пользовательских параметров.  
  
- VAR_TIMEVALUEONLY игнорировать часть даты во время синтаксического анализа.  
  
- VAR_DATEVALUEONLY пропускать части времени во время синтаксического анализа.  
  
 *lcid*  
 Указывает идентификатор языкового стандарта для использования для преобразования. Дополнительные сведения об идентификаторах языков см. в разделе [идентификаторы языка](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 *lpszFormat*  
 Форматирование строки аналогичную `printf` форматирования строки. Каждый форматирование кода, предшествует процента ( `%`) выполните вход, заменен соответствующим `COleDateTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Функции времени выполнения см. в разделе [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Дополнительные сведения. Значение и значение коды форматирования для `Format` являются:  
  
- `%H` Часов в текущей даты  
  
- `%M` Минут в текущий час  
  
- `%S` Секунд в текущую минуту  
  
- `%%` Знак процента  
  
 *nFormatID*  
 Идентификатор ресурса для управления форматом строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащее значение даты/времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Если состояние данного объекта `COleDateTime` объект имеет значение null, возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс ATL_IDS_DATETIME_INVALID.  
  
 Краткое описание три формы для этой функции выглядит следующим образом:  
  
 `Format`( *dwFlags*, *lcid*)  
 Эта форма форматирует значение с помощью языка спецификаций (идентификаторы языковых стандартов) для даты и времени. С параметрами по умолчанию, эта форма, печатаются дату и время, если части времени — 0 (полночь), в противном случае он выводит только дату или часть даты имеет значение 0 (30 декабря 1899 г.), в противном случае оно печатается только время. Если значение даты и времени равно 0 (30 декабря 1899 г., полночь), эта форма с параметрами по умолчанию будет печататься полуночи.  
  
 `Format`( *lpszFormat*)  
 Эта форма форматирует значение с помощью строки формата, которая содержит специальные коды форматирования, которым предшествует знак процента (%), как показано на `printf`. Строка форматирования передается в качестве параметра функции. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) справочника по библиотеке времени выполнения.  
  
 `Format`( *nFormatID*)  
 Эта форма форматирует значение с помощью строки формата, которая содержит специальные коды форматирования, которым предшествует знак процента (%), как показано на `printf`. Строка форматирования — это ресурс. Идентификатор этого ресурса строка передается в качестве параметра. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в *Справочник по библиотеке времени выполнения*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>  COleDateTime::GetAsDBTIMESTAMP  
 Вызовите этот метод для получения времени в `COleDateTime` объекта в виде `DBTIMESTAMP` структуру данных.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *DBTS*  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сохраняет полученное время для упоминаемого *dbts* структуры. `DBTIMESTAMP` Структура данных инициализируется при помощи этой функции будет иметь его `fraction` имеет нулевое значение члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>  COleDateTime::GetAsSystemTime  
 Вызовите этот метод для получения времени в `COleDateTime` объекта в виде `SYSTEMTIME` структуру данных.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *sysTime*  
 Ссылку на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру для получения преобразованного даты и времени по максимуму `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если выполнение прошло успешно; Значение FALSE, если преобразование завершается неудачей, или если `COleDateTime` объект имеет значение NULL или недопустим.  
  
### <a name="remarks"></a>Примечания  
 `GetAsSystemTime` сохраняет полученное время для упоминаемого *sysTime* объекта. `SYSTEMTIME` Структура данных инициализируется при помощи этой функции будет иметь его `wMilliseconds` имеет нулевое значение члена.  
  
 См. в разделе [GetStatus](#getstatus) для содержатся дополнительные сведения о сведениях о состоянии в `COleDateTime` объекта.  
  
##  <a name="getasudate"></a>  COleDateTime::GetAsUDATE  
 Вызовите этот метод для получения времени в `COleDateTime` объекта в виде `UDATE` структуру данных.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *UDATE*  
 Ссылку на `UDATE` структуру для получения преобразованного даты и времени по максимуму `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если выполнение прошло успешно; Значение FALSE, если преобразование завершается неудачей, или если `COleDateTime` объект имеет значение NULL или недопустим.  
  
### <a name="remarks"></a>Примечания  
 Объект `UDATE` структура представляет дату «распакованы».  
  
##  <a name="getcurrenttime"></a>  COleDateTime::GetCurrentTime  
 Вызывайте эту функцию статического члена, чтобы вернуть значение текущей даты и времени.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>  COleDateTime::GetDay  
 Возвращает день месяца, представляемое этим значением даты и времени.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День месяца, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если день не может быть получено.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 1 до 31.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 Возвращает день месяца, представляемое этим значением даты и времени.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День недели, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если день недели не может быть получено.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемые значения диапазона от 1 до 7, где 1 = воскресенье, 2 = понедельник и т. д.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 Возвращает день года, представляемое этим значением даты и времени.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День года, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить день года.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемые значения в диапазоне от 1 до 366, где 1 января = 1.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 Возвращает час, представляемое этим значением даты и времени.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Час, представленный значение этой `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить час.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 23.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 Возвращает минуту, представляемое этим значением даты и времени.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минуты, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить минуты.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 59.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 См. в примере [GetHour](#gethour).  
  
##  <a name="getmonth"></a>  COleDateTime::GetMonth  
 Возвращает месяц, представляемое этим значением даты и времени.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Месяца, представленный значение этой `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить месяца.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 1 до 12.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 См. в примере [GetDay](#getday).  
  
##  <a name="getsecond"></a>  COleDateTime::GetSecond  
 Возвращает второй, представляемое этим значением даты и времени.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Второй, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить второй.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 59.  
  
> [!NOTE]
>  `COleDateTime` Класс не поддерживает корректировочных секунд.  
  
 Дополнительные сведения о реализации для `COleDateTime`, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 См. в примере [GetHour](#gethour).  
  
##  <a name="getstatus"></a>  COleDateTime::GetStatus  
 Получает состояние (действия) заданного `COleDateTime` объекта.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние данного объекта `COleDateTime` значение. При вызове метода `GetStatus` на `COleDateTime` объект создан со значением по умолчанию, он будет возвращать допустимый. При вызове метода `GetStatus` на `COleDateTime` объект инициализирован со конструктор, имеющим значение null, `GetStatus` вернет значение null. См. в разделе **"Примечания"** Дополнительные сведения.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется `DateTimeStatus` перечислимый тип, который определен в `COleDateTime` класса.  
  
```  
enum DateTimeStatus  
{  
   error = -1,  
   valid = 0,  
   invalid = 1,    // Invalid date (out of range, etc.)  
   null = 2,       // Literally has no value  
};  
```  
  
 Краткое описание этих значений состояния см. в следующем списке:  
  
- `COleDateTime::error` Указывает, что произошла ошибка при попытке получить часть значения даты и времени.  
  
- `COleDateTime::valid` Указывает, что этот `COleDateTime` объект является допустимым.  
  
- `COleDateTime::invalid` Указывает, что этот `COleDateTime` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- `COleDateTime::null` Указывает, что этот `COleDateTime` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)  
  
 Состояние `COleDateTime` становится недействительным в следующих случаях:  
  
-   Если он имеет значение из `VARIANT` или `COleVariant` значение, которое не удалось преобразовать значение даты и времени.  
  
-   Если он имеет значение из `time_t`, `SYSTEMTIME`, или `FILETIME` значение, которое не удалось преобразовать значение допустимые дату и время.  
  
-   Если его значение установлено `SetDateTime` с недопустимые значения параметров.  
  
-   Если этот объект опыт работы с переполнения или потери значимости во время назначения, арифметические операции, а именно, `+=` или `-=`.  
  
-   Если недопустимое значение был назначен этот объект.  
  
-   Если состояние этого объекта было задано явно недопустимыми с помощью `SetStatus`.  
  
 Дополнительные сведения об операциях, которые может задать состояние на недопустимый см. в следующих функций-членов:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [оператор +, -](#operator_add_-)  
  
- [оператор +=-=](#operator_add_eq_-_eq)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>  COleDateTime::GetYear  
 Возвращает год, представляемое этим значением даты и времени.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Год, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если год не может быть получено.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 100 до 9999, включающую год с веком.  
  
 Сведения о других функций-членов, которые запрашивают значение этой `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 См. в примере [GetDay](#getday).  
  
##  <a name="m_dt"></a>  COleDateTime::m_dt  
 Базовый `DATE` структуры для этого `COleDateTime` объекта.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в `DATE` объект, к которому указатель, возвращаемый этой функцией изменится значение этой `COleDateTime` объекта. Это не приводит к изменению состояния этого `COleDateTime` объекта.  
  
 Дополнительные сведения о реализации `DATE` объекта, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="m_status"></a>  COleDateTime::m_status  
 Содержит состояние данного объекта `COleDateTime` объекта.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Примечания  
 Тип этого элемента данных является перечисляемым типом `DateTimeStatus`, который определен в `COleDateTime` класса. См. в разделе [COleDateTime::GetStatus](#getstatus) сведения.  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). См. в разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания для этого элемента данных.  
  
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
 Эти перегруженных операторах присваивания копирования исходное значение даты и времени в данный `COleDateTime` объекта. Краткое описание для каждой из этих перегружать следующим операторы присваивания:  
  
- **оператор = (** `dateSrc` **)** значение и состояния операнда копируются в это `COleDateTime` объекта.  
  
- **оператор = (** *varSrc* **)** Если преобразование [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) значение (или [COleVariant](../../mfc/reference/colevariant-class.md) объект) для даты и времени (VT_ Дата) выполнена успешно, преобразованное значение копируется в данную коллекцию `COleDateTime` объекта и его состояние имеет значение на допустимое. Если преобразование не выполнено успешно, этот объект является значение ноль (30 декабря 1899 г., полночь) и его состояние на недопустимый.  
  
- **оператор = (** `dtSrc` **)** `DATE` значение копируется в это `COleDateTime` объекта и его состояние имеет значение на допустимое.  
  
- **оператор = (** `timeSrc` **)** `time_t` или `__time64_t` преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта присваивается допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый.  
  
- **оператор = (** *systimeSrc* **)** [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта присваивается допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый.  
  
- **оператор = (** `udate` **)** `UDATE` преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта присваивается допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый. Объект `UDATE` структура представляет дату «распакованы». См. в разделе функция [VarDateFromUdate](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-vardatefromudate) для получения дополнительных сведений.  
  
- **оператор = (** `filetimeSrc` **)** [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, состояние этого объекта присваивается допустимым; в противном случае оно устанавливается на недопустимый. `FILETIME` использует всеобщее скоординированное время (UTC), поэтому, если передать время в формате UTC в структуре, результаты преобразуется из времени в формате UTC в местное время и будет храниться в виде варианта времени. Это происходит так же, как и в Visual C++ 6.0 и Visual C++ .NET 2003 с пакетом обновления 2. См. в разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в пакете SDK для Windows, Дополнительные сведения.  
  
 Дополнительные сведения см. в разделе [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) запись в пакете Windows SDK.  
  
 Дополнительные сведения о `time_t` тип данных, см. в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) работать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структур в пакете Windows SDK.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_add_-"></a>  COleDateTime::operator +, -  
 Добавление и вычитание `ColeDateTime` значения.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 `COleDateTime` они представляют абсолютное время. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) представляют относительное время. Первые два операторы позволяют сложения и вычитания `COleDateTimeSpan` значение из `COleDateTime` значение. Третий оператор позволяет вычесть единицу `COleDateTime` значения из другого выдавала `COleDateTimeSpan` значение.  
  
 Если любой из операндов имеет значение null, состояние результата `COleDateTime` имеет значение null.  
  
 Если полученный в результате `COleDateTime` значение выходит за пределы допустимых значений, состояние, `COleDateTime` недопустимое значение.  
  
 Если любой из операндов является недопустимым, и другой не равно null, состояние результата `COleDateTime` недопустимое значение.  
  
 **+** И **-** операторов будет утверждать, если `COleDateTime` объекта задано значение null. См. в разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTime::operator +=-=  
 Добавление и вычитание `ColeDateTime` значение из этого `COleDateTime` объекта.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `COleDateTimeSpan` значение в и из этого `COleDateTime`. Если любой из операндов имеет значение null, состояние результата `COleDateTime` имеет значение null.  
  
 Если полученный в результате `COleDateTime` значение выходит за пределы допустимых значений, состояние данного объекта `COleDateTime` значение на недопустимый.  
  
 Если любой из операндов является недопустимым, и другие не равно null, состояние результата `COleDateTime` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
 **+=** И **-=** операторов будет утверждать, если `COleDateTime` объекта задано значение null. См. в разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
 Дополнительные сведения о граничные значения для `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_date"></a>  COleDateTime::operator даты  
 Преобразует `ColeDateTime` значение в `DATE`.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает `DATE` объект, значение которого копируется из этого `COleDateTime` объекта. Дополнительные сведения о реализации `DATE` объекта, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 `DATE` Оператор будет утверждать, если `COleDateTime` объекта задано значение null. См. в разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
##  <a name="parsedatetime"></a>  COleDateTime::ParseDateTime  
 Анализирует строку для чтения значения даты и времени.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszDate*  
 Указатель на заканчивающуюся нулем строку, который анализируется. Дополнительные сведения см. в разделе "Заметки".  
  
 *dwFlags*  
 Указывает флаги для параметров языкового стандарта и синтаксического анализа. Один или несколько из следующих флагов:  
  
- LOCALE_NOUSEROVERRIDE использовать параметры языкового стандарта системы по умолчанию, а не пользовательские параметры пользователя.  
  
- VAR_TIMEVALUEONLY игнорировать часть даты во время синтаксического анализа.  
  
- VAR_DATEVALUEONLY пропускать части времени во время синтаксического анализа.  
  
 *lcid*  
 Указывает идентификатор языкового стандарта для использования для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если строка успешно преобразован в значение даты и времени, в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если строка была успешно преобразована в даты и времени значение, значение этого `COleDateTime` объекта имеет значение этого значения и его статус на допустимый.  
  
> [!NOTE]
>  Год значения должны находиться в диапазоне от 100 до 9999 г. включительно.  
  
 *LpszDate* параметр может принимать различные форматы. Например следующие строки содержат форматов допустимые даты и времени:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`  
  
 Обратите внимание, что также влияет на код языка ли формат строки является приемлемой для преобразования в значение даты и времени.  
  
 В случае VAR_DATEVALUEONLY значения времени присваивается 0, или полуночи. В случае VAR_TIMEVALUEONLY значение будет присвоено даты 0, то есть 30 декабря 1899 г.  
  
 Если не удалось преобразовать строку в значение даты и времени или в случае отсутствия численного переполнения, состояние данного объекта `COleDateTime` объекта является недопустимым.  
  
 Дополнительные сведения о границах и внедрению `COleDateTime` значения, см. в статье [даты и времени: Поддержка модели автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="setdate"></a>  COleDateTime::SetDate  
 Задает дату данной `COleDateTime` объекта.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nYear*, *nMonth*, *nDay*  
 Указать компоненты даты, который необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение данного объекта `COleDateTime` объекта заданы успешно; в противном случае — значение 1. Это возвращаемое значение зависит от `DateTimeStatus` перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функция-член.  
  
### <a name="remarks"></a>Примечания  
 Дата устанавливается указанные значения. Время задается время 0, полночь.  
  
 См. в следующей таблице, границы для значения параметров:  
  
|Параметр|Границы|  
|---------------|------------|  
|*nYear*|100 - 9999|  
|*nMonth*|1 - 12|  
|*nDay*|0 - 31|  
  
 При переполнении числа месяца, оно преобразуется в правильный день следующего месяца и месяца и/или года увеличивается соответствующим образом. День нулевое значение указывает последний день предыдущего месяца. Поведение совпадает со значением `SystemTimeToVariantTime`.  
  
 Если недопустимое значение даты, указанный параметрами, состояния этого объекта присваивается `COleDateTime::invalid`. Следует использовать [GetStatus](#getstatus) для проверки допустимости `DATE` значение и не следует предполагать, что значение [m_dt](#m_dt) останется без изменений.  
  
 Ниже приведены некоторые примеры значений дат.  
  
|*nYear*|*nMonth*|*nDay*|Значение|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29 февраля 2000 г.|  
|1776|7|4|4 июля 1776|  
|1925|4|35|35 1925 апреля (Недопустимая дата)|  
|10000|1|1|1 января 10000 (Недопустимая дата)|  
  
 Чтобы задать дату и время, см. в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 Задает дату и время `COleDateTime` объекта.  
  
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
 *nYear*, *nMonth*, *nDay*, *основе Nчас*, *Nмин.*, *nSec*  
 Указать компоненты даты и времени, который необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение данного объекта `COleDateTime` объекта заданы успешно; в противном случае — значение 1. Это возвращаемое значение зависит от `DateTimeStatus` перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функция-член.  
  
### <a name="remarks"></a>Примечания  
 См. в следующей таблице, границы для значения параметров:  
  
|Параметр|Границы|  
|---------------|------------|  
|*nYear*|100 - 9999|  
|*nMonth*|1 - 12|  
|*nDay*|0 - 31|  
|*основе Nчас*|0 - 23|  
|*Nмин.*|0 - 59|  
|*nSec*|0 - 59|  
  
 При переполнении числа месяца, оно преобразуется в правильный день следующего месяца и месяца и/или года увеличивается соответствующим образом. День нулевое значение указывает последний день предыдущего месяца. Поведение совпадает со значением [SystemTimeToVariantTime](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-systemtimetovarianttime).  
  
 Если значение даты или времени, указанный параметрами не допускается, состояния этого объекта имеет значение недопустимо, а значение этого объекта не изменяется.  
  
 Ниже приведены некоторые примеры значений времени.  
  
|*основе Nчас*|*Nмин.*|*nSec*|Значение|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Недопустимо|  
|9|60|0|Недопустимо|  
  
 Ниже приведены некоторые примеры значений дат.  
  
|*nYear*|*nMonth*|*nDay*|Значение|  
|-------------|--------------|------------|-----------|  
|1995|4|15|15 апреля 1995|  
|1789|7|14|17 июля 1789|  
|1925|2|30|Недопустимо|  
|10000|1|1|Недопустимо|  
  
 Чтобы задать только дата, см. в разделе [COleDateTime::SetDate](#setdate). Чтобы задать только время, см. в разделе [COleDateTime::SetTime](#settime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 См. в примере [GetStatus](#getstatus).  
  
##  <a name="setstatus"></a>  COleDateTime::SetStatus  
 Задает состояние данного объекта `COleDateTime` объекта.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Новое значение состояния для данного `COleDateTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется `DateTimeStatus` перечислимый тип, который определен в `COleDateTime` класса. См. в разделе [COleDateTime::GetStatus](#getstatus) сведения.  
  
> [!CAUTION]
>  Эта функция служит для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для задания состояния **null** или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTime](#setdatetime) задать состояние объекта на основании значения источника.  
  
### <a name="example"></a>Пример  
 См. в примере [GetStatus](#getstatus).  
  
##  <a name="settime"></a>  COleDateTime::SetTime  
 Задает время `COleDateTime` объекта.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *основе Nчас*, *Nмин.*, *nSec*  
 Указать компоненты времени, который необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение данного объекта `COleDateTime` объекта заданы успешно; в противном случае — значение 1. Это возвращаемое значение зависит от `DateTimeStatus` перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функция-член.  
  
### <a name="remarks"></a>Примечания  
 Время установлено указанные значения. Дата устанавливается дата 0, то есть 30 декабря 1899 г.  
  
 См. в следующей таблице, границы для значения параметров:  
  
|Параметр|Границы|  
|---------------|------------|  
|*основе Nчас*|0 - 23|  
|*Nмин.*|0 - 59|  
|*nSec*|0 - 59|  
  
 Если значение с указанными параметрами не допускается, время состояния этого объекта имеет значение недопустимо и значение этого объекта не изменяется.  
  
 Ниже приведены некоторые примеры значений времени.  
  
|*основе Nчас*|*Nмин.*|*nSec*|Значение|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Недопустимо|  
|9|60|0|Недопустимо|  
  
 Чтобы задать дату и время, см. в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. в разделе следующих функций-членов:  
  
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
 См. в примере [SetDate](#setdate).  
  
## <a name="see-also"></a>См. также  
 [Класс COleVariant](../../mfc/reference/colevariant-class.md)   
 [Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




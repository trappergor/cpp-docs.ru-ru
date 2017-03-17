---
title: "Класс COleDateTime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 34
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
ms.openlocfilehash: ecb32876e55c9801b28fefa1a189508ffbc8b78c
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetime-class"></a>Класс COleDateTime
Инкапсулирует `DATE` тип данных, используемый в OLE-автоматизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Создает объект `COleDateTime`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Создает строковое представление `COleDateTime` объекта.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **DBTIMESTAMP** структуру данных.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Этот метод вызывается для получения времени в `COleDateTime` объекта в виде [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру данных.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Этот метод вызывается для получения времени в `COleDateTime` как **UDATE** структуру данных.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Создает `COleDateTime` объект, представляющий текущее время (статическая функция-член).|  
|[COleDateTime::GetDay](#getday)|Возвращает день, это `COleDateTime` представляет объект (1 – 31).|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, это `COleDateTime` представляет (воскресенье = 1).|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Возвращает день года, это `COleDateTime` представляет (1 января = 1).|  
|[COleDateTime::GetHour](#gethour)|Возвращает час, это `COleDateTime` представляет (0-23).|  
|[COleDateTime::GetMinute](#getminute)|Возвращает минуты `COleDateTime` представляет (0 – 59).|  
|[COleDateTime::GetMonth](#getmonth)|Возвращает месяц, это `COleDateTime` представляет объект (1 – 12).|  
|[COleDateTime::GetSecond](#getsecond)|Возвращает второй `COleDateTime` представляет (0 – 59).|  
|[COleDateTime::GetStatus](#getstatus)|Возвращает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::GetYear](#getyear)|Возвращает год, это `COleDateTime` представляет.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Считывает значение даты и времени из строки и задает значение `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Задает значение этого `COleDateTime` объекта указанное значение только дату.|  
|[COleDateTime::SetDateTime](#setdatetime)|Задает значение этого `COleDateTime` значение указанных даты и времени.|  
|[COleDateTime::SetStatus](#setstatus)|Задает состояние (действия) это `COleDateTime` объекта.|  
|[COleDateTime::SetTime](#settime)|Задает значение этого `COleDateTime` объекта указанное значение только со временем.|  
  
### <a name="public-operators"></a>Открытые операторы  

|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::operator == COleDateTime::operator<,></,>](#coledatetime_relational_operators)|Сравнить два `COleDateTime` значения.|  
|[COleDateTime::operator + COleDateTime::operator-](#operator_add_-)|Добавление и вычитание `COleDateTime` значения.|  
|[COleDateTime::operator +=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Добавление и вычитание `COleDateTime` значение из этого `COleDateTime` объекта.|  
|[COleDateTime::operator =](#operator_eq)|Копирует `COleDateTime` значение.|  
|[COleDateTime::operator даты, даты COleDateTime::operator *](#operator_date)|Преобразует `COleDateTime` значение в `DATE` или `DATE*`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Содержит базовый **даты** для этого `COleDateTime` объекта.|  
|[COleDateTime::m_status](#m_status)|Содержит состояние данного объекта `COleDateTime` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleDateTime`не имеет базового класса.  
  
 Это один из возможных типов для [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) тип данных OLE-автоматизации. A `COleDateTime` значение представляет абсолютное значение даты и времени.  
  
 `DATE` Тип реализуется как значение с плавающей запятой. Дни отсчитываются от 30 декабря 1899 г., в полночь. Ниже приведены некоторые даты и связанных с ними значений:  
  
|Дата|Значение|  
|----------|-----------|  
|Полночь 29 декабря 1899 г.,|-1.0|  
|29 декабря 1899 г., 6 по|-1.25|  
|Полночь 30 декабря 1899 г.,|0,0|  
|Полночь 31 декабря 1899 г.,|1,0|  
|1 января 1900 г., 6: 00.|2.25|  
  
> [!CAUTION]
>  Обратите внимание, в приведенной выше таблице, хотя значения дня становиться отрицательными до полуночи 30 декабря 1899 г., значения времени дня не. Например 6:00 AM всегда представляется дробные значения от 0,25 независимо от того, целое число, представляющее день (после 30 декабря 1899 г.) минус (до 30 декабря 1899 г.). Это означает, что простое сравнение чисел с плавающей точкой ошибочно отсортировать `COleDateTime` 6:00 AM 12/29/1899 года как представляющий **позже** чем та, представляющий 07:00:00 в тот же день.  
  
 `COleDateTime` Класс обрабатывает даты с 1 января 100 до 31 декабря 9999 года. `COleDateTime` Класс использует григорианский календарь; не поддерживает юлианскому дат. `COleDateTime`не учитывается летнее время. (См. [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Можно использовать `%y` формат для извлечения только для дат, начиная с 1900 года двумя цифрами. Если вы используете `%y` формат даты до 1900, код создает ПРЕДПОЛОЖЕНИЕ сбоя.  
  
 Этот тип также используется для представления значений только дату или только со временем. По соглашению Дата 0 (30 декабря 1899 г.) используется для значения только во время и время 00:00 (полночь) используется для значения только дату.  
  
 При создании `COleDateTime` с использованием даты не более 100 дата является правильным, но последующие вызовы `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, и `GetSecond` завершиться с ошибкой и возвращают значение -1. Ранее можно использовать заданные двумя цифрами, но даты должны быть 100 или больше в MFC версии 4.2 и более поздних версий.  
  
 Чтобы избежать проблем, укажите дату из четырех цифр. Например:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#1;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Основные арифметические операции для `COleDateTime` значения используйте вспомогательный класс [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan`значения определяют интервал времени. Взаимосвязь между этими классами вида между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Дополнительные сведения о `COleDateTime` и `COleDateTimeSpan` классы, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>Реляционные операторы COleDateTime  
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
 [!code-cpp[NVC_ATLMFC_Utilities&#13;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Пример  
 The operators **>=**, **\<=**, **>**, and **<**, will assert if the `COleDateTime` object is set to null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#170;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>COleDateTime::COleDateTime  
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
 Существующий `COleDateTime` скопировать в новый объект `COleDateTime` объект.  
  
 *varSrc*  
 Существующий **VARIANT** структуру данных (возможно `COleVariant` объект) для преобразования в значение даты и времени ( `VT_DATE`) и скопировать в новый `COleDateTime` объекта.  
  
 `dtSrc`  
 Даты и времени ( **даты**) значения, которое копируется в новый `COleDateTime` объекта.  
  
 `timeSrc`  
 Объект `time_t` или **__time64_t** значение преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 *systimeSrc*  
 Объект `SYSTEMTIME` структура преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 `filetimeSrc`  
 Объект `FILETIME` структура преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта. Обратите внимание, что `FILETIME` использует всеобщее скоординированное время (UTC), поэтому при передаче в структуру местного времени, результаты могут оказаться неверными. В разделе [время файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Указать значения даты и времени, которое необходимо скопировать в новый `COleDateTime` объекта.  
  
 `wDosDate`, `wDosTime`  
 Значения даты и времени MS-DOS, преобразуется в значение даты и времени и скопировать в новый `COleDateTime` объекта.  
  
 `dbts`  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структура, содержащая текущее время.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создать `COleDateTime` объекты, инициализированные в указанное значение. В следующей таблице показаны допустимые диапазоны для каждого компонента даты и времени:  
  
|Компонент даты и времени|Допустимый диапазон значений|  
|--------------------------|-----------------|  
|год|100 – 9999|  
|месяц|0 – 12|  
|дн|0 – 31|  
|ч|0 – 23|  
|мин|0 – 59|  
|second|0 – 59|  
  
 Обратите внимание, что зависит от фактического верхнюю границу компонент дня на основе месяц и год компонентов. Дополнительные сведения см. в разделе **SetDate** или `SetDateTime` функции-члены.  
  
 Ниже приводится краткое описание каждого конструктора:  
  
- `COleDateTime(`**)** Создает `COleDateTime` объект инициализируется значением 0 (полночь 30 декабря 1899 г.).  
  
- `COleDateTime(``dateSrc` **)** Создает `COleDateTime` из существующего `COleDateTime` объекта.  
  
- `COleDateTime(`*varSrc* **)** создает `COleDateTime` объекта. Пытается преобразовать `VARIANT` структуры или [COleVariant](../../mfc/reference/colevariant-class.md) объекта даты и времени ( `VT_DATE`) значение. Если это преобразование выполнено успешно, преобразованное значение копируется в новый `COleDateTime` объекта. Если это не так, значение `COleDateTime` имеет значение 0 (полночь 30 декабря 1899 г.) и его статус на недопустимое.  
  
- `COleDateTime(``dtSrc` **)** Создает `COleDateTime` объекта из **даты** значение.  
  
- `COleDateTime(``timeSrc` **)** Создает `COleDateTime` объекта из `time_t` значение.  
  
- `COleDateTime(`*systimeSrc* **)** создает `COleDateTime` объекта из `SYSTEMTIME` значение.  
  
- `COleDateTime(``filetimeSrc` **)** Создает `COleDateTime` объекта из `FILETIME` значение. . Обратите внимание, что `FILETIME` использует всеобщее скоординированное время (UTC), поэтому при передаче в структуру местного времени, результаты могут оказаться неверными. В разделе [время файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
- `COleDateTime(``nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Создает `COleDateTime` объект из указанного числовые значения.  
  
- `COleDateTime(``wDosDate`, `wDosTime` **)** Создает `COleDateTime` объект из указанного значения даты и времени MS-DOS.  
  
 Дополнительные сведения о `time_t` тип данных, в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) работать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  Конструктор с помощью **DBTIMESTAMP** параметр доступен, только если включено OLEDB.h.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#2;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>COleDateTime::Format  
 Создает отформатированное представление значения даты и времени.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Указывает один из следующих флагов языкового стандарта:  
  
- `LOCALE_NOUSEROVERRIDE`Используйте параметры языкового стандарта системы по умолчанию, вместо пользовательских параметров.  
  
- `VAR_TIMEVALUEONLY`Пропустить часть даты во время синтаксического анализа.  
  
- `VAR_DATEVALUEONLY`Пропускать части времени во время синтаксического анализа.  
  
 `lcid`  
 Указывает идентификатор языкового стандарта, используемый для преобразования. Дополнительные сведения об идентификаторах языков см. в разделе [идентификаторы языка](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 `lpszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Каждый форматирование кода, ставится в процентах ( `%`) выполните вход, заменен соответствующим `COleDateTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Во время выполнения функции [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) подробнее. Значение и значение коды форматирования для `Format` являются:  
  
- `%H`Часы в текущий день  
  
- `%M`Минут в течение текущего часа  
  
- `%S`Секунды в текущей минуте  
  
- `%%`Знак процента  
  
 `nFormatID`  
 Идентификатор ресурса для управления форматом строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащее значение даты и времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Если это состояние `COleDateTime` объект имеет значение null, возвращается пустая строка. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс `ATL_IDS_DATETIME_INVALID`.  
  
 Краткое описание трех форм для этой функции выглядит следующим образом:  
  
 `Format`( `dwFlags`, `lcid`)  
 Эта форма форматирует значение с помощью спецификации языка (идентификаторы языковых стандартов) для даты и времени. С параметрами по умолчанию, эта форма, печатаются дату и время, если части времени равно 0 (полночь), в этом случае она будет напечатана только дату или часть даты — 0 (30 декабря 1899 г.), в этом случае печатаются только время. Если значение даты и времени равно 0 (30 декабря 1899 г., полночь), эта форма с параметрами по умолчанию, напечатает полуночи.  
  
 `Format`( `lpszFormat`)  
 Эта форма форматирует значение с помощью строки формата, который содержит специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка формата передается как параметр функции. Дополнительные сведения о кодах форматирования см. в разделе [strftime wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в справочнике библиотеки времени выполнения.  
  
 `Format`( `nFormatID`)  
 Эта форма форматирует значение с помощью строки формата, который содержит специальные коды форматирования, которым предшествует знак процента (%), как в `printf`. Строка форматирования является ресурсом. Идентификатор этого ресурса строка передается как параметр. Дополнительные сведения о кодах форматирования см. в разделе [strftime wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в *Справочник по библиотеке времени выполнения*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#3;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **DBTIMESTAMP** структуру данных.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dbts`  
 Ссылку на [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сохраняет полученное время в структуре `dbts`, на которую указана ссылка. **DBTIMESTAMP** структуру данных, инициализации, эта функция будет иметь его **дробь** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#4;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде `SYSTEMTIME` структуру данных.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *sysTime*  
 Ссылку на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры для получения значения преобразованных даты и времени из `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения; **false** в случае неудачного преобразования, или если `COleDateTime` объект **NULL** или недопустим.  
  
### <a name="remarks"></a>Примечания  
 `GetAsSystemTime`сохраняет итоговое время упоминаемого *sysTime* объекта. `SYSTEMTIME` Структуру данных, инициализации, эта функция будет иметь его **wMilliseconds** член равен нулю.  
  
 В разделе [GetStatus](#getstatus) для содержатся дополнительные сведения о состоянии в `COleDateTime` объекта.  
  
##  <a name="getasudate"></a>COleDateTime::GetAsUDATE  
 Этот метод вызывается для получения времени в `COleDateTime` объекта в виде **UDATE** структуру данных.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `udate`  
 Ссылку на **UDATE** структуры для получения значения преобразованных даты и времени из `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения; **false** в случае неудачного преобразования, или если `COleDateTime` объект **NULL** или недопустим.  
  
### <a name="remarks"></a>Примечания  
 Объект **UDATE** структура представляет дату «Распакованная».  
  
##  <a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 Вызовите это статическая функция-член для возврата значения текущей даты и времени.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#5;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>COleDateTime::GetDay  
 Возвращает день месяца, представленный это значение даты и времени.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День месяца, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить день.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемого значения в диапазоне от 1 до 31.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities №&6;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 Возвращает день месяца, представленный это значение даты и времени.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День недели, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить день недели.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращают значения в диапазоне от 1 до 7, где 1 = воскресенье, 2 = понедельник и т. д.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#7;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 Возвращает день года, представленный это значение даты и времени.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 День года, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить день года.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемого значения в диапазоне от 1 до 366, где 1 января = 1.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities №&8;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>COleDateTime::GetHour  
 Возвращает час, представляемое этим значением даты и времени.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Час, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить значение часа.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемого значения в диапазоне от 0 до 23.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities №&9;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>COleDateTime::GetMinute  
 Возвращает минуты, представляемое этим значением даты и времени.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Минуты, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить минуты.  
  
### <a name="remarks"></a>Примечания  
 Диапазон допустимых возвращаемых значений от 0 до 59.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 В примере показано [GetHour](#gethour).  
  
##  <a name="getmonth"></a>COleDateTime::GetMonth  
 Возвращает месяц, представляемое этим значением даты и времени.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Месяц, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить месяца.  
  
### <a name="remarks"></a>Примечания  
 Допустимые возвращаемого значения в диапазоне от 1 до 12.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 В примере показано [GetDay](#getday).  
  
##  <a name="getsecond"></a>COleDateTime::GetSecond  
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
  
 Дополнительные сведения о реализации для `COleDateTime`, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Пример  
 В примере показано [GetHour](#gethour).  
  
##  <a name="getstatus"></a>COleDateTime::GetStatus  
 Возвращает состояние (действия) заданного `COleDateTime` объекта.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние данного объекта `COleDateTime` значение. При вызове метода **GetStatus** на `COleDateTime` объект создан со значением по умолчанию, он будет возвращать допустимое. При вызове метода **GetStatus** на `COleDateTime` объект инициализируется с конструктора, равным null, **GetStatus** вернет значение null. В разделе **примечания** подробнее.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется **DateTimeStatus** перечислимый тип, который определен в `COleDateTime` класса.  
  
 `enum DateTimeStatus`  
  
 `{`  
  
 `error = -1,`  
  
 `valid = 0,`  
  
 `invalid = 1,    // Invalid date (out of range, etc.)`  
  
 `null = 2,       // Literally has no value`  
  
 `};`  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- `COleDateTime::error`Указывает, что произошла ошибка при попытке получить часть значения даты и времени.  
  
- **COleDateTime::valid** указывает это `COleDateTime` объект является допустимым.  
  
- **COleDateTime::invalid** указывает это `COleDateTime` недопустимый объект; то есть, его значение может быть неправильным.  
  
- **COleDateTime::null** указывает это `COleDateTime` объект имеет значение null, то есть, что для этого объекта не указано никакого значения. (Значение «NULL» в смысле базы данных «предложений having не значение» в отличие от C++ **NULL**.)  
  
 Состояние `COleDateTime` недопустимый объект в следующих случаях:  
  
-   Если его значение из **VARIANT** или `COleVariant` значение, которое не удалось преобразовать значение даты и времени.  
  
-   Если его значение из `time_t`, `SYSTEMTIME`, или `FILETIME` значение, которое не удалось преобразовать значение допустимые дату и время.  
  
-   Если его значение определяется `SetDateTime` с недопустимые значения параметров.  
  
-   Если этот объект опыт переполнения или потери значимости во время назначения арифметические операции, а именно, `+=` или `-=`.  
  
-   Если недопустимое значение был назначен этот объект.  
  
-   Если состояние этого объекта было задано явно недопустимого с помощью `SetStatus`.  
  
 Дополнительные сведения об операциях, которые может задать состояние недопустимый см. следующие функции-члены:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [оператор +, -](#operator_add_-)  
  
- [оператор +=-=](#operator_add_eq_-_eq)  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#10;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>COleDateTime::GetYear  
 Возвращает год, представляемое этим значением даты и времени.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Год, представленный значением этого `COleDateTime` объекта или `COleDateTime::error` Если не удалось получить год.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое диапазон допустимых значений — от 100 до 9999, включая век.  
  
 Сведения о функциях-членах, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 В примере показано [GetDay](#getday).  
  
##  <a name="m_dt"></a>COleDateTime::m_dt  
 Базовый **даты** структуры для этого `COleDateTime` объекта.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в **даты** объект, к которому указатель, возвращаемый этой функцией приведет к изменению значения этого `COleDateTime` объекта. Не изменяет состояние данного объекта `COleDateTime` объекта.  
  
 Дополнительные сведения о реализации **даты** объекта, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="m_status"></a>COleDateTime::m_status  
 Содержит состояние данного объекта `COleDateTime` объекта.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Примечания  
 Тип этого элемента данных — перечислимый тип **DateTimeStatus**, которая определена в `COleDateTime` класса. В разделе [COleDateTime::GetStatus](#getstatus) подробные сведения.  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать встроенные функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). В разделе `SetStatus` для дальнейшего предостережения о явном задании этого элемента данных.  
  
##  <a name="operator_eq"></a>COleDateTime::operator =  
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
 Скопируйте эти перегруженных операторах присваивания исходного значения даты и времени в эту `COleDateTime` объекта. Краткое описание всех этих перегружать следующие операторы присваивания:  
  
- **оператор = (** `dateSrc` **)** копируется в это значение и состояния операнда `COleDateTime` объекта.  
  
- **оператор = (** *varSrc* **)** Если преобразование [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) значение (или [COleVariant](../../mfc/reference/colevariant-class.md) объект) для даты и времени ( `VT_DATE`) — успешно, преобразованное значение копируется в это `COleDateTime` объекта и его состояние имеет значение на допустимое. Если преобразование не удалось, этот объект имеет значение ноль (30 декабря 1899 г., полночь) и его статус на недопустимое.  
  
- **оператор = (** `dtSrc` **)** **даты** значение копируется в этот `COleDateTime` объекта и его состояние имеет значение на допустимое.  
  
- **оператор = (** `timeSrc` **)** `time_t` или **__time64_t** преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, этот объект имеет значение допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый.  
  
- **оператор = (** *systimeSrc* **)** [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, этот объект имеет значение допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый.  
  
- **оператор = (** `udate` **)** **UDATE** преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, этот объект имеет значение допустимым; Если операция завершилась неудачей, он устанавливается на недопустимый. Объект **UDATE** структура представляет дату «Распакованная». Функции [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) для получения дополнительных сведений.  
  
- **оператор = (** `filetimeSrc` **)** [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) преобразуется и копируются в это значение `COleDateTime` объекта. Если преобразование прошло успешно, этот объект имеет значение допустимым; в противном случае оно устанавливается на недопустимый. `FILETIME`использует всеобщее скоординированное время (UTC), поэтому при передаче время в формате UTC в структуре, результатов преобразуется в формате UTC в местное время и будет храниться как variant времени. Это происходит так же, как в Visual C++ 6.0 и Visual C++ .NET 2003 с пакетом обновления 2. В разделе [время файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
 Дополнительные сведения см. в разделе [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) запись в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о `time_t` тип данных, в разделе [время](../../c-runtime-library/reference/time-time32-time64.md) работать в *Справочник по библиотеке времени выполнения*.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структур в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_add_-"></a>COleDateTime::operator +, -  
 Добавление и вычитание **ColeDateTime** значения.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Примечания  
 `COleDateTime`они представляют абсолютное время. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) представляют относительное время. Первые два операторы позволяют сложения и вычитания `COleDateTimeSpan` значение из `COleDateTime` значение. Третий оператор позволяет вычесть единицу `COleDateTime` значение из другого выдавала `COleDateTimeSpan` значение.  
  
 Если любой из операндов имеет значение null, состояние конечного `COleDateTime` имеет значение null.  
  
 Если полученный `COleDateTime` находится за пределами допустимых значений состояния, `COleDateTime` недопустимое значение.  
  
 Если любой из операндов недопустимо и другой не равно null, состояние результата `COleDateTime` недопустимое значение.  
  
 ** + ** И ** - ** операторы будут утверждать, если `COleDateTime` объекта задано значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null в разделе [m_status](#m_status) переменной-члена.  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#12;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTime::operator +=-=  
 Добавление и вычитание **ColeDateTime** значение из этого `COleDateTime` объекта.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `COleDateTimeSpan` значение в и из этого `COleDateTime`. Если любой из операндов имеет значение null, состояние конечного `COleDateTime` имеет значение null.  
  
 Если полученный `COleDateTime` находится за пределами допустимых значений, это состояние `COleDateTime` значение недопустимым.  
  
 Если любой из операндов недопустимо и другие не равно null, состояние результата `COleDateTime` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null в разделе [m_status](#m_status) переменной-члена.  
  
 ** += ** И ** -= ** операторы будут утверждать, если `COleDateTime` объекта задано значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_date"></a>COleDateTime::operator даты  
 Преобразует **ColeDateTime** значение в **даты**.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает **даты** объект, значение которого копируется из этого `COleDateTime` объекта. Дополнительные сведения о реализации **даты** объекта, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 **Даты** оператор проверяет Если `COleDateTime` объекта задано значение null. В разделе [COleDateTime реляционные операторы](#coledatetime_relational_operators) пример.  
  
##  <a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 Анализирует строку для чтения значения даты и времени.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszDate`  
 Указатель нулем строку, которая анализируется. Дополнительные сведения см. в разделе "Заметки".  
  
 `dwFlags`  
 Указывает флаги для региональных параметров и анализа. Один или несколько из следующих флагов:  
  
- **LOCALE_NOUSEROVERRIDE** используйте параметры языкового стандарта системы по умолчанию, а не пользовательские настройки.  
  
- **VAR_TIMEVALUEONLY** пропустить часть даты во время синтаксического анализа.  
  
- **VAR_DATEVALUEONLY** пропускать части времени во время синтаксического анализа.  
  
 `lcid`  
 Указывает идентификатор языкового стандарта, используемый для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если строка был успешно преобразован в значение даты и времени, в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Если строка был успешно преобразован в даты и времени значение, значение этого `COleDateTime` имеет значение этого значения и его статус на допустимое.  
  
> [!NOTE]
>  Значения года должно находиться в диапазоне от 100 до 9999 г. включительно.  
  
 `lpszDate` Параметр может принимать разнообразные форматы. Например следующие строки содержат форматы допустимые даты и времени:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year,`  
  
 `// even in a 'short date' format`  
  
 Обратите внимание, что также влияет на код языка ли формат строки приемлемо для преобразования в значение даты и времени.  
  
 В случае использования **VAR_DATEVALUEONLY**, время имеет значение времени 0 или полуночи. В случае использования **VAR_TIMEVALUEONLY**, дата, имеет значение даты 0, то есть 30 декабря 1899 г.  
  
 Если строка не удалось преобразовать значение даты и времени, или если была численного переполнения, это состояние `COleDateTime` недопустимый объект.  
  
 Дополнительные сведения о границах и реализацию `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="setdate"></a>COleDateTime::SetDate  
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
 Нуль, если значение этого `COleDateTime` объекта заданы успешно; в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Дата устанавливается с указанными значениями. Время задано время 0, полночь.  
  
 См. в следующей таблице границы для значения параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
  
 При переполнении числа месяца, оно преобразуется в правильный день следующего месяца и месяца или года увеличивается соответствующим образом. День нулевое значение указывает последний день предыдущего месяца. Поведение такое же, как `SystemTimeToVariantTime`.  
  
 Если недопустимое значение даты, определяются параметрами, присваивается состояние данного объекта **COleDateTime::invalid**. Следует использовать [GetStatus](#getstatus) для проверки допустимости **даты** значение и не следует предполагать, что значение [m_dt](#m_dt) , останутся неизменными.  
  
 Ниже приведены некоторые примеры значений даты.  
  
|`nYear`|`nMonth`|`nDay`|Значение|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29 февраля 2000 г.|  
|1776|7|4|4 июля 1776|  
|1925|4|35|35 1925 апреля (Недопустимая дата)|  
|10000|1|1|1 января 10000 (Недопустимая дата)|  
  
 Чтобы установить дату и время, в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&11;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>COleDateTime::SetDateTime  
 Задает дату и время `COleDateTime` объект.  
  
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
 Указывает компоненты даты и времени, необходимо скопировать в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение этого `COleDateTime` объекта заданы успешно; в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 См. в следующей таблице границы для значения параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 При переполнении числа месяца, оно преобразуется в правильный день следующего месяца и месяца или года увеличивается соответствующим образом. День нулевое значение указывает последний день предыдущего месяца. Поведение такое же, как [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450).  
  
 Если значение даты или времени, определяются параметрами является недопустимым, недопустим и значение этого объекта задано состояние этого объекта не изменяется.  
  
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
|1995|4|15|15 апреля-1995|  
|1789|7|14|17 июля 1789|  
|1925|2|30|Недопустимо|  
|10000|1|1|Недопустимо|  
  
 Для установки только даты, см. [COleDateTime::SetDate](#setdate). Установить только время, в разделе [COleDateTime::SetTime](#settime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 В примере показано [GetStatus](#getstatus).  
  
##  <a name="setstatus"></a>COleDateTime::SetStatus  
 Задает состояние данного объекта `COleDateTime` объекта.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Новое значение для этого состояния `COleDateTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется **DateTimeStatus** перечислимый тип, который определен в `COleDateTime` класса. В разделе [COleDateTime::GetStatus](#getstatus) подробные сведения.  
  
> [!CAUTION]
>  Эта функция предназначена для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего будет использоваться для присвоения состоянию `null` или **недопустимый**. Обратите внимание, что оператор присваивания ( [оператор =](#eq)) и [SetDateTime](#setdatetime) задать состояние объекта на основании исходного значения.  
  
### <a name="example"></a>Пример  
 В примере показано [GetStatus](#getstatus).  
  
##  <a name="settime"></a>COleDateTime::SetTime  
 Задает время `COleDateTime` объект.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nHour`, `nMin`, `nSec`  
 Указывает компоненты времени должно быть скопировано в это `COleDateTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если значение этого `COleDateTime` объекта заданы успешно; в противном случае — 1. Это возвращаемое значение зависит от **DateTimeStatus** перечисляемый тип. Дополнительные сведения см. в разделе [SetStatus](#setstatus) функции-члена.  
  
### <a name="remarks"></a>Примечания  
 Время установлено указанные значения. Дата устанавливается дата 0, то есть 30 декабря 1899 г.  
  
 См. в следующей таблице границы для значения параметра:  
  
|Параметр|Границы|  
|---------------|------------|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 Если время недопустимое значение, указанное в параметрах недопустимо и значение этого объекта задано состояние этого объекта не изменяется.  
  
 Ниже приведены некоторые примеры значений времени.  
  
|`nHour`|`nMin`|`nSec`|Значение|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Недопустимо|  
|9|60|0|Недопустимо|  
  
 Чтобы установить дату и время, в разделе [COleDateTime::SetDateTime](#setdatetime).  
  
 Сведения о функции-члены, значение этого запроса `COleDateTime` объекта, см. следующие функции-члены:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Дополнительные сведения о границы `COleDateTime` значения, см. в статье [даты и времени: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Пример  
 В примере показано [SetDate](#setdate).  
  
## <a name="see-also"></a>См. также  
 [Класс COleVariant](../../mfc/reference/colevariant-class.md)   
 [Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)





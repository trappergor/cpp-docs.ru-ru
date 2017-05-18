---
title: "Класс CTime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 22e488a1c5760c342ce79c42cd8a48c911715b23
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="ctime-class"></a>Класс CTime
Представляет абсолютное время и дату.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTime  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|Создает `CTime` объекты различными способами.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTime::Format](#format)|Преобразует `CTime` объекта в форматированную строку, в зависимости от местного часового пояса.|  
|[CTime::FormatGmt](#formatgmt)|Преобразует `CTime` объекта в форматированную строку, в зависимости от времени UTC.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Преобразует время сведениями, хранящимися в `CTime` объекта к структуре DBTIMESTAMP Win32-совместимой.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Преобразует время сведениями, хранящимися в `CTime` объекта в Win32-совместимый [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.|  
|[CTime::GetCurrentTime](#getcurrenttime)|Создает `CTime` объект, который представляет текущее время (статическая функция-член).|  
|[CTime::GetDay](#getday)|Возвращает представляют день по `CTime` объекта.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, представленный `CTime` объекта.|  
|[CTime::GetGmtTm](#getgmttm)|Разбивает `CTime` объекта на компоненты, зависимости от времени UTC.|  
|[CTime::GetHour](#gethour)|Возвращает час, представленный `CTime` объекта.|  
|[CTime::GetLocalTm](#getlocaltm)|Разбивает `CTime` объекта на компоненты, зависимости от местного часового пояса.|  
|[CTime::GetMinute](#getminute)|Возвращается значение минут, представленного `CTime` объекта.|  
|[CTime::GetMonth](#getmonth)|Возвращает значение месяца, представленный `CTime` объекта.|  
|[CTime::GetSecond](#getsecond)|Возвращает второй, представленного `CTime` объекта.|  
|[CTime::GetTime](#gettime)|Возвращает **__time64_t** значение для данного `CTime` объекта.|  
|[CTime::GetYear](#getyear)|Возвращает год, представленный `CTime` объекта.|  
|[CTime::Serialize64](#serialize64)|Выполняет сериализацию данных в и из архива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор + -](#operator_add_-)|Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.|  
|[оператор +=-=](#operator_add_eq_-_eq)|Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.|  
|[оператор =](#operator_eq)|Оператор присваивания.|  
|[оператор ==,< ,="">](#ctime_comparison_operators)|Операторы сравнения.|  
  
## <a name="remarks"></a>Примечания  
 `CTime`не имеет базового класса.  
  
 `CTime`на основе значения общего скоординированного времени (UTC), что эквивалентно формате UTC (по Гринвичу, GMT). В разделе [управление временем](../../c-runtime-library/time-management.md) сведения о том, как определяется часовой пояс.  
  
 При создании `CTime` , установите `nDST` в значение 0, чтобы указать, что стандартное время действует, или значение больше 0, чтобы указать, что летнего времени действует значение меньше нуля, чтобы указать вычислений код библиотеки времени выполнения C ли стандартное время или летнего времени действует. `tm_isdst` — это обязательное поле. Если не задано, его значение не определено и возвращаемое значение [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) непредсказуем. Если `timeptr` указывает на структуру tm, возвращенный предыдущим вызовом [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), или [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` поле содержит правильное значение.  
  
 Вспомогательный класс, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), представляющий интервал времени.  
  
 `CTime` И `CTimeSpan` классы не предназначены для наследования. Так как нет виртуальных функций, размер `CTime` и `CTimeSpan` объекты — ровно 8 байт. Большинство функций — членов приведены в коде.  
  
> [!NOTE]
>  Дата верхний предел — 12/31/3000. Нижний предел составляет 1/1/1970 г. 12:00:00 AM GMT.  
  
 Дополнительные сведения об использовании `CTime`, см. в статьях [даты и времени](../../atl-mfc-shared/date-and-time.md), и [управление временем](../../c-runtime-library/time-management.md) в справочнике библиотеки времени выполнения.  
  
> [!NOTE]
>  `CTime` Структура изменен с MFC 7.1 на MFC 8.0. При сериализации `CTime` структуры с помощью `operator <<` в MFC 8.0 или более поздней версии, полученный файл будет невозможно читать в предыдущих версиях MFC.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>Операторы сравнения CTime  
 Операторы сравнения.  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 `time`  
 Сравниваемый объект `CTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эти операторы сравнивают два раза абсолютным и возвращают **true** Если условие имеет значение true; в противном случае **false**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>CTime::CTime  
 Создает новый `CTime` объект инициализируется с указанного времени.  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `timeSrc`  
 Указывает `CTime` объект, который уже существует.  
  
 `time`  
 Объект **__time64_t** значения времени число секунд после 1 января 1970 г. UTC. Обратите внимание, что это будет исправлено местному времени. Например, если в Нью-Йорке и создать `CTime` объекта, передавая параметр 0, [CTime::GetMonth](#getmonth) возвращает 12.  
  
 В Visual C++ версии 6.0 и более ранних версиях `time` был значение `time_t`. Visual C++ .NET и более поздних версий преобразует `time_t` параметр **__time64_t**.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Указывает значения даты и времени, который необходимо скопировать в новый `CTime` объекта.  
  
 `nDST`  
 Указывает, действует ли летнее время. Может иметь одно из трех значений:  
  
- `nDST`значение времени 0Standard вступает в действие.  
  
- `nDST`Задайте значение больше, чем 0Daylight фактически — экономии времени.  
  
- `nDST`задано значение меньше, чем 0The по умолчанию. Автоматически вычисляет стандартное время или летнее время действует ли.  
  
 `wDosDate`, `wDosTime`  
 Значения даты и времени MS-DOS преобразовывается в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 `st`  
 Объект [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) структура преобразуется в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 `ft`  
 Объект [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) структура преобразуется в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 DBTS  
 Ссылка на DBTIMESTAMP структуру, содержащую текущее местное время.  
  
### <a name="remarks"></a>Примечания  
 Каждый конструктор описан ниже.  
  
- **CTime();** Создает неинициализированный `CTime` объекта. Этот конструктор позволяет определить `CTime` объекта массивы. Такие массивы с допустимым раз перед использованием необходимо инициализировать.  
  
- **CTime (const CTime &);** Создает `CTime` объекта из другого `CTime` значение.  
  
- **CTime (__time64_t);** Создает `CTime` объекта из **__time64_t** типа. Этот конструктор ожидает, что время в формате UTC, а результат преобразуется в местное время перед сохранением результат.  
  
- **CTime (int, int,...);** Создает `CTime` объекта из компонентов местного времени с каждым компонентом ограничен следующими диапазонами:  
  
    |Компонент|Диапазон|  
    |---------------|-----------|  
    |`nYear`|1970-3000|  
    |`nMonth`|1-12|  
    |`nDay`|1-31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Этот конструктор создает соответствующее преобразование в формат UTC. Отладочная версия библиотеки классов Microsoft Foundation утверждения, если один или несколько компонентов времени выходят за пределы диапазона. Необходимо проверить перед вызовом аргументы. Этот конструктор ожидает местное время.  
  
- **CTime (WORD, Microsoft WORD);** Создает `CTime` объект из указанного значения даты и времени MS-DOS. Этот конструктор ожидает местное время.  
  
- **CTime (const SYSTEMTIME &);** Создает `CTime` объекта из `SYSTEMTIME` структуры. Этот конструктор ожидает местное время.  
  
- **CTime (const FILETIME &);** Создает `CTime` объекта из `FILETIME` структуры. Скорее всего, вы не будете использовать `CTime FILETIME` инициализации напрямую. Если вы используете `CFile` объекта для работы с файлом `CFile::GetStatus` получает метку времени файла через `CTime` объект инициализирован с `FILETIME` структуры. Этот конструктор использует временной интервал, в зависимости от времени UTC и автоматически преобразует значение в местное время перед сохранением результат.  
  
    > [!NOTE]
    >  Конструктор с помощью **DBTIMESTAMP** параметр доступен, только если включено OLEDB.h.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуры в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. См. также [MS-DOS даты и времени](http://msdn.microsoft.com/library/windows/desktop/ms724503) запись в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>CTime::Format  
 Вызовите эту функцию-член для создания отформатированное представление значения даты и времени.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Коды, предшествует процента форматирования ( `%`) выполните вход, заменен соответствующим `CTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. В описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) список кодов форматирования.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Если это состояние `CTime` объект имеет значение null, возвращается пустая строка.  
  
 Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 общего скоординированного времени (UTC).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>CTime::FormatGmt  
 Создает строку форматирования, которая соответствует этому `CTime` объекта.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Задает строку форматирования, аналогичную `printf` строка форматирования. В описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) подробные сведения.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Значение времени не преобразуется и таким образом отражает время UTC.  
  
 Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 общего скоординированного времени (UTC).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CTime::Format](#format).  
  
##  <a name="getasdbtimestamp"></a>CTime::GetAsDBTIMESTAMP  
 Вызовите эту функцию-член для преобразования времени сведениями, хранящимися в `CTime` объекта к структуре DBTIMESTAMP Win32-совместимой.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dbts`  
 Ссылка на DBTIMESTAMP структуру, содержащую текущее местное время.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сохраняет полученное время в структуре `dbts`, на которую указана ссылка. **DBTIMESTAMP** данных структуру, инициализированную эта функция будет иметь его **дробь** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>CTime::GetAsSystemTime  
 Вызовите эту функцию-член для преобразования времени сведениями, хранящимися в `CTime` объекта в Win32-совместимый [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *timeDest*  
 Ссылку на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет хранить значение преобразованного даты и времени `CTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение true, если успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `GetAsSystemTime`сохраняет полученное время упоминаемого *timeDest* структуры. `SYSTEMTIME` Данных структуру, инициализированную эта функция будет иметь его **wMilliseconds** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>CTime::GetCurrentTime  
 Возвращает `CTime` , представляющий текущее время.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает текущую системную дату и время в формате UTC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>CTime::GetDay  
 Возвращает представляют день по `CTime` объекта.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает день месяца, в зависимости от местного времени в диапазоне от 1 до 31.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, который использует внутренний, статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>CTime::GetDayOfWeek  
 Возвращает день недели, представленный `CTime` объекта.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает день недели, локального времени; 1 = воскресенье, 2 = понедельник, 7 = суббота.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>CTime::GetGmtTm  
 Возвращает **tm структура** , содержащий развернутого времени, содержащихся в данном `CTime` объекта.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `ptm`  
 Указывает на буфер, который получит данные времени. Если указатель относится **NULL**, создается исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на заполняться **tm структура** определенное время включаемого файла. З. В разделе [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) структуры макета.  
  
### <a name="remarks"></a>Примечания  
 `GetGmtTm`Возвращает в формате UTC.  
  
 Параметр `ptm` не может иметь значение `NULL`. Если требуется вернуться к старому поведению, в котором `ptm` может быть `NULL` для указания, что следует использовать во внутренней, статически выделенный буфер, отменить `_SECURE_ATL`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>CTime::GetHour  
 Возвращает час, представленный `CTime` объекта.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает час, локального времени в диапазоне от 0 до 23.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>CTime::GetLocalTm  
 Возвращает **tm структура** содержащий развернутого времени, содержащихся в данном `CTime` объекта.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `ptm`  
 Указывает на буфер, который получит данные времени. Если указатель относится **NULL**, создается исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на заполняться **tm структура** определенное время включаемого файла. З. В разделе [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) структуры макета.  
  
### <a name="remarks"></a>Примечания  
 `GetLocalTm`Возвращает местное время.  
  
 Параметр `ptm` не может иметь значение `NULL`. Если требуется вернуться к старому поведению, в котором `ptm` может быть `NULL` для указания, что следует использовать во внутренней, статически выделенный буфер, отменить `_SECURE_ATL`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>CTime::GetMinute  
 Возвращается значение минут, представленного `CTime` объекта.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минуты в зависимости от местного времени в диапазоне от 0 до 59.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHour](#gethour).  
  
##  <a name="getmonth"></a>CTime::GetMonth  
 Возвращает значение месяца, представленный `CTime` объекта.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает месяц, локального времени в диапазоне от 1 до 12 (1 = январь).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetDay](#getday).  
  
##  <a name="getsecond"></a>CTime::GetSecond  
 Возвращает второй, представленного `CTime` объекта.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает второй, локального времени в диапазоне от 0 до 59.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHour](#gethour).  
  
##  <a name="gettime"></a>CTime::GetTime  
 Возвращает **__time64_t** значение для данного `CTime` объекта.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **GetTime** Возвращает время в секундах между текущим `CTime` объекта и 1 января 1970 года.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>CTime::GetYear  
 Возвращает год, представленный `CTime` объекта.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает год, локального времени в диапазоне от января 1,1970 для января 18 2038 года (включительно).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает `GetLocalTm`, которая использует внутреннюю статически выделенный буфер. Данные в этом буфере будут перезаписаны из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetDay](#getday).  
  
##  <a name="operator_eq"></a>CTime::operator =  
 Оператор присваивания.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `time`  
 Значение нового даты и времени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор назначения перегруженных время источника копирует в этот `CTime` объекта. Хранилище системных часов в `CTime` объекта не зависит от часового пояса. Преобразование часовой пояс не требуется во время назначения.  
  
##  <a name="operator_add_-"></a>CTime::operator +, -  
 Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 *интервал времени*  
 `CTimeSpan` Добавить или вычесть объекта.  
  
 `time`  
 `CTime` Объект, который будет вычтен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CTime` или `CTimeSpan` объект, представляющий результат операции.  
  
### <a name="remarks"></a>Примечания  
 `CTime`объекты представляют абсолютное время `CTimeSpan` объекты представляют относительного времени. Первые два операторы позволяют сложения и вычитания `CTimeSpan` объекты в и из `CTime` объектов. Третий оператор можно вычесть единицу `CTime` объекта из другого выдавала `CTimeSpan` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTime::operator +=-=  
 Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 `CTimeSpan` Добавить или вычесть объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities #160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>CTime::Serialize64  
  
> [!NOTE]
>  Этот метод доступен только в проектах MFC.  
  
 Сериализует данные, связанные с переменной-члена или из архива.  
  
```  
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 `CArchive` Объект, который требуется обновить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CArchive` объекта.  
  
## <a name="see-also"></a>См. также  
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)




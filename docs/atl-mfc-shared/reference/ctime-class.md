---
title: "Класс CTime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTime
- CTime
- ATL::CTime
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
translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 56b8b5c3574a7a53a4e259412b1b1326973bcac9
ms.lasthandoff: 02/28/2017

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
|[CTime::Format](#format)|Преобразует `CTime` объект в форматированную строку, в зависимости от местного часового пояса.|  
|[CTime::FormatGmt](#formatgmt)|Преобразует `CTime` объект в форматированную строку, в зависимости от времени UTC.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Преобразует время сведения, хранящиеся в `CTime` объекта на структуру Win32-совместимых DBTIMESTAMP.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Преобразует время сведения, хранящиеся в `CTime` объект в совместимый Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.|  
|[CTime::GetCurrentTime](#getcurrenttime)|Создает `CTime` объект, представляющий текущее время (статическая функция-член).|  
|[CTime::GetDay](#getday)|Возвращает день представляют по `CTime` объекта.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Возвращает день недели, представленный `CTime` объекта.|  
|[CTime::GetGmtTm](#getgmttm)|Разбивает `CTime` объекта на компоненты, зависимости в формате UTC.|  
|[CTime::GetHour](#gethour)|Возвращает час, представленный `CTime` объекта.|  
|[CTime::GetLocalTm](#getlocaltm)|Разбивает `CTime` объекта на компоненты, зависимости от местного часового пояса.|  
|[CTime::GetMinute](#getminute)|Возвращается значение минут, представленного `CTime` объекта.|  
|[CTime::GetMonth](#getmonth)|Возвращает значение месяца, представленного `CTime` объекта.|  
|[CTime::GetSecond](#getsecond)|Возвращает второй, представленного `CTime` объекта.|  
|[CTime::GetTime](#gettime)|Возвращает **__time64_t** значение для данного `CTime` объекта.|  
|[CTime::GetYear](#getyear)|Возвращает год, представленный `CTime` объекта.|  
|[CTime::Serialize64](#serialize64)|Выполняет сериализацию данных или из архива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор +.](#operator_add_-)|Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.|  
|[оператор += – =](#operator_add_eq_-_eq)|Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.|  
|[оператор =](#operator_eq)|Оператор присваивания.|  
|[оператор ==,< ,="">](#ctime_comparison_operators)|Операторы сравнения.|  
  
## <a name="remarks"></a>Примечания  
 `CTime`не имеет базового класса.  
  
 `CTime`значения основаны на всемирного координированного времени (UTC), что эквивалентно формате UTC (по Гринвичу, GMT). В разделе [управление временем](../../c-runtime-library/time-management.md) для получения сведений об определении часового пояса.  
  
 При создании `CTime` объекта `nDST` параметра равным 0, чтобы указать, что стандартное время действует, или значение больше 0, чтобы указать, что летнего времени действует значение меньше нуля, чтобы указать вычислений код библиотеки времени выполнения C ли стандартное время или летнее время действует. `tm_isdst` — это обязательное поле. Если не задано, его значение не определено и возвращаемое значение [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) непредсказуемо. Если `timeptr` указывает на структуру tm, возвращенный предыдущим вызовом [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), или [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` поле содержит правильное значение.  
  
 Вспомогательный класс, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), представляющий интервал времени.  
  
 `CTime` И `CTimeSpan` классы не предназначены для наследования. Поскольку нет виртуальных функций, размер `CTime` и `CTimeSpan` объектов имеет ровно 8 байт. Большинство функций-членов приведены в коде.  
  
> [!NOTE]
>  Первая дата в ограничение составляет 12/31/3000. Нижняя граница — 1/1/1970 12:00:00 AM GMT.  
  
 Дополнительные сведения об использовании `CTime`, см. в статьях [даты и времени](../../atl-mfc-shared/date-and-time.md), и [управление временем](../../c-runtime-library/time-management.md) в справочнике библиотеки времени выполнения.  
  
> [!NOTE]
>  `CTime` Структура изменен с MFC 7.1 в MFC 8.0. При сериализации `CTime` структуры с помощью `operator <<` в MFC 8.0 или более поздней версии, полученный файл нельзя будет прочитать в более старых версиях MFC.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="a-namectimecomparisonoperatorsa--ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>Операторы сравнения CTime  
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
 Эти операторы сравнивают два раза абсолютный и возвращают **true** Если условие имеет значение true; в противном случае **false**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#161;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="a-namectimea--ctimectime"></a><a name="ctime"></a>CTime::CTime  
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
 Указывает `CTime` объекта, который уже существует.  
  
 `time`  
 Объект **__time64_t** значения времени число секунд после 1 января 1970 г. UTC. Обратите внимание, что это будет скорректирована местное время. Например, если в Нью-Йорке и создать `CTime` объекта, передав параметр 0, [CTime::GetMonth](#getmonth) возвращает 12.  
  
 В Visual C++ версии 6.0 и более ранних версиях `time` был значение `time_t`. Visual C++ .NET и более поздних преобразует `time_t` параметр **__time64_t**.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Указывает значения даты и времени, которое необходимо скопировать в новый `CTime` объекта.  
  
 `nDST`  
 Указывает, действует ли летнее время. Может иметь одно из трех значений:  
  
- `nDST`значение времени 0Standard вступает в действие.  
  
- `nDST`Задайте значение больше 0Daylight фактически является экономия времени.  
  
- `nDST`задано значение меньше, чем 0The по умолчанию. Автоматически вычисляет стандартное время или летнее время действует ли.  
  
 `wDosDate`, `wDosTime`  
 Значения даты и времени MS-DOS, преобразуется в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 `st`  
 Объект [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) структура преобразуется в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 `ft`  
 Объект [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) структура преобразуется в значение даты и времени и скопировать в новый `CTime` объекта.  
  
 DBTS  
 Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.  
  
### <a name="remarks"></a>Примечания  
 Каждый конструктор описан ниже.  
  
- **CTime(); ** Создает неинициализированный объект `CTime` объект. Этот конструктор позволяет определить `CTime` объекта массивы. Такие массивы с допустимое время перед использованием необходимо инициализировать.  
  
- **CTime (const CTime &); ** Создает `CTime` из другого объекта `CTime` значение.  
  
- **CTime (__time64_t); ** Создает `CTime` объекта из **__time64_t** типа. Этот конструктор ожидает, что время в формате UTC и преобразует результат в местное время перед сохранением результат.  
  
- **CTime (int, int,...) ** Создает `CTime` объекта из компонентов местного времени с каждым компонентом ограничен следующими диапазонами:  
  
    |Компонент|Диапазон|  
    |---------------|-----------|  
    |`nYear`|1970–3000|  
    |`nMonth`|1–12|  
    |`nDay`|1–31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Этот конструктор создает соответствующее преобразование в формат UTC. Отладочная версия библиотеки классов Microsoft Foundation утверждений, если один или несколько компонентов времени выходят за пределы диапазона. Необходимо проверить перед вызовом аргументы. Этот конструктор ожидает местное время.  
  
- **CTime (WORD, WORD); ** Создает `CTime` объект из указанного значения даты и времени MS-DOS. Этот конструктор ожидает местное время.  
  
- **CTime (const SYSTEMTIME &); ** Создает `CTime` объекта из `SYSTEMTIME` структуры. Этот конструктор ожидает местное время.  
  
- **CTime (const FILETIME &); ** Создает `CTime` объекта из `FILETIME` структуры. Скорее всего, вы не будете использовать `CTime FILETIME` инициализации напрямую. При использовании `CFile` объекта для работы с файлом `CFile::GetStatus` получает метку времени файла через `CTime` объект инициализирован с `FILETIME` структуры. Этот конструктор предполагается, что время, в зависимости от времени UTC и автоматически преобразует значение в местное время перед сохранением результат.  
  
    > [!NOTE]
    >  Конструктор с помощью **DBTIMESTAMP** параметр доступен, только если включено OLEDB.h.  
  
 Дополнительные сведения см. в разделе [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) и [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. См. также [MS-DOS даты и времени](http://msdn.microsoft.com/library/windows/desktop/ms724503) запись в [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#148;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="a-nameformata--ctimeformat"></a><a name="format"></a>CTime::Format  
 Вызовите эту функцию-член для создания отформатированное представление значения даты и времени.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Форматирование кодов, ставится в процентах ( `%`) выполните вход, заменен соответствующим `CTime` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Во время выполнения функции [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) список кодов форматирования.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Если это состояние `CTime` объект имеет значение null, возвращается пустая строка.  
  
 Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 всеобщее скоординированное время (UTC).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#149;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="a-nameformatgmta--ctimeformatgmt"></a><a name="formatgmt"></a>CTime::FormatGmt  
 Создает форматированную строку, соответствующий этому `CTime` объекта.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `pszFormat`  
 Задает строку форматирования аналогично `printf` строка форматирования. Во время выполнения функции [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) подробные сведения.  
  
 `nFormatID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Значение времени не преобразуется и таким образом отражает время UTC.  
  
 Этот метод вызывает исключение, если значение даты и времени для форматирования не находится в диапазоне от полуночи 1 января 1970 года до 31 декабря 3000 всеобщее скоординированное время (UTC).  
  
### <a name="example"></a>Пример  
 В примере показано [CTime::Format](#format).  
  
##  <a name="a-namegetasdbtimestampa--ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>CTime::GetAsDBTIMESTAMP  
 Вызов этой функции-члена для преобразования времени сведения, хранящиеся в `CTime` объекта на структуру Win32, совместимой с DBTIMESTAMP.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dbts`  
 Ссылка на структуру DBTIMESTAMP, содержащую текущее местное время.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сохраняет полученное время в структуре `dbts`, на которую указана ссылка. **DBTIMESTAMP** структуру данных, инициализации, эта функция будет иметь его **дробь** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#150;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="a-namegetassystemtimea--ctimegetassystemtime"></a><a name="getassystemtime"></a>CTime::GetAsSystemTime  
 Вызов этой функции-члена для преобразования времени сведения, хранящиеся в `CTime` в Win32-совместимый [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *timeDest*  
 Ссылку на [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая будет хранить значение преобразованный даты и времени `CTime` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение true, если выполнено успешно; в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 `GetAsSystemTime`сохраняет итоговое время упоминаемого *timeDest* структуры. `SYSTEMTIME` Структуру данных, инициализации, эта функция будет иметь его **wMilliseconds** член равен нулю.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#151;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="a-namegetcurrenttimea--ctimegetcurrenttime"></a><a name="getcurrenttime"></a>CTime::GetCurrentTime  
 Возвращает `CTime` , представляющий текущее время.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает текущую системную дату и время в формате UTC (UTC).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#152;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="a-namegetdaya--ctimegetday"></a><a name="getday"></a>CTime::GetDay  
 Возвращает день представляют по `CTime` объекта.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает день месяца, локального времени в диапазоне от 1 до 31.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, который использует внутренний, статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#153;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="a-namegetdayofweeka--ctimegetdayofweek"></a><a name="getdayofweek"></a>CTime::GetDayOfWeek  
 Возвращает день недели, представленный `CTime` объекта.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает день недели, на основе локального времени; 1 = воскресенье, 2 = понедельник, 7 = суббота.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#154;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="a-namegetgmttma--ctimegetgmttm"></a><a name="getgmttm"></a>CTime::GetGmtTm  
 Возвращает **структура tm** , содержащий декомпозиции времени, содержащихся в данном `CTime` объекта.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `ptm`  
 Указывает на буфер, который получит данные времени. Если этот указатель имеет **NULL**, создается исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на заполняться **структура tm** определенное время включаемого файла. З. В разделе [gmtime _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) структуры макета.  
  
### <a name="remarks"></a>Примечания  
 `GetGmtTm`Возвращает время UTC.  
  
 Параметр `ptm` не может иметь значение `NULL`. Если вы хотите вернуться к старому поведению, в котором `ptm` может быть `NULL` для указания использования внутренних, статически выделенный буфер, отменить `_SECURE_ATL`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#155;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="a-namegethoura--ctimegethour"></a><a name="gethour"></a>CTime::GetHour  
 Возвращает час, представленный `CTime` объекта.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает час, локального времени в диапазоне от 0 до 23.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#156;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="a-namegetlocaltma--ctimegetlocaltm"></a><a name="getlocaltm"></a>CTime::GetLocalTm  
 Возвращает **структура tm** содержащий декомпозиции времени, содержащихся в данном `CTime` объекта.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `ptm`  
 Указывает на буфер, который получит данные времени. Если этот указатель имеет **NULL**, создается исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на заполняться **структура tm** определенное время включаемого файла. З. В разделе [gmtime _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) структуры макета.  
  
### <a name="remarks"></a>Примечания  
 `GetLocalTm`Возвращает локальное время.  
  
 Параметр `ptm` не может иметь значение `NULL`. Если вы хотите вернуться к старому поведению, в котором `ptm` может быть `NULL` для указания использования внутренних, статически выделенный буфер, отменить `_SECURE_ATL`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#157;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="a-namegetminutea--ctimegetminute"></a><a name="getminute"></a>CTime::GetMinute  
 Возвращается значение минут, представленного `CTime` объекта.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает минуты, локального времени в диапазоне от 0 до 59.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 В примере показано [GetHour](#gethour).  
  
##  <a name="a-namegetmontha--ctimegetmonth"></a><a name="getmonth"></a>CTime::GetMonth  
 Возвращает значение месяца, представленного `CTime` объекта.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает месяц локального времени в диапазоне от 1 до 12 (1 = январь).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 В примере показано [GetDay](#getday).  
  
##  <a name="a-namegetseconda--ctimegetsecond"></a><a name="getsecond"></a>CTime::GetSecond  
 Возвращает второй, представленного `CTime` объекта.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает второй, локального времени в диапазоне от 0 до 59.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 В примере показано [GetHour](#gethour).  
  
##  <a name="a-namegettimea--ctimegettime"></a><a name="gettime"></a>CTime::GetTime  
 Возвращает **__time64_t** значение для данного `CTime` объекта.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **GetTime** возвращает количество секунд между текущим `CTime` объекта и 1 января 1970 года.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#158;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="a-namegetyeara--ctimegetyear"></a><a name="getyear"></a>CTime::GetYear  
 Возвращает год, представленный `CTime` объекта.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает год, локального времени в диапазоне от января 1,1970 для января 18 2038 года (включительно).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает функцию `GetLocalTm`, которая использует внутренний статически выделенный буфер. Данные в этот буфер перезаписывается из-за других вызовов `CTime` функции-члены.  
  
### <a name="example"></a>Пример  
 В примере показано [GetDay](#getday).  
  
##  <a name="a-nameoperatoreqa--ctimeoperator-"></a><a name="operator_eq"></a>CTime::operator =  
 Оператор присваивания.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `time`  
 Значение новой даты и времени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор назначения перегруженных копирует время источника в это `CTime` объекта. Внутреннее время хранения в `CTime` объекта не зависит от часового пояса. Преобразование часового пояса нет необходимости во время назначения.  
  
##  <a name="a-nameoperatoradd-a--ctimeoperator---"></a><a name="operator_add_-"></a>CTime::operator +, -  
 Эти операторы сложения и вычитания `CTimeSpan` и `CTime` объектов.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Параметры  
 *timeSpan*  
 `CTimeSpan` Объект добавляемое или вычитаемое.  
  
 `time`  
 `CTime` Объект, который будет вычтен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CTime` или `CTimeSpan` объект, представляющий результат операции.  
  
### <a name="remarks"></a>Примечания  
 `CTime`объекты представляют абсолютное время `CTimeSpan` объекты представляют относительного времени. Первые два операторы позволяют сложения и вычитания `CTimeSpan` объекты в и из `CTime` объектов. Третий оператор позволяет вычесть единицу `CTime` из другого для получения объекта `CTimeSpan` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#159;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>CTime::operator +=-=  
 Эти операторы сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 `CTimeSpan` Объект добавляемое или вычитаемое.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTime` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `CTimeSpan` и обратно это `CTime` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#160;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="a-nameserialize64a--ctimeserialize64"></a><a name="serialize64"></a>CTime::Serialize64  
  
> [!NOTE]
>  Этот метод доступен только в проектах MFC.  
  
 Сериализует данные, связанные с переменной-члена в или из архива.  
  
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
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




---
title: "Класс CTimeSpan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
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
ms.openlocfilehash: 5c76411f6c1302d406b07cc79d9c544e3ad8c43b
ms.lasthandoff: 02/24/2017

---
# <a name="ctimespan-class"></a>Класс CTimeSpan
Количество времени, которые внутренне хранятся как количество секунд в промежутке времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Создает `CTimeSpan` объекты различными способами.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Преобразует `CTimeSpan` в форматированную строку.|  
|[CTimeSpan::GetDays](#getdays)|Возвращает значение, представляющее число завершения дней в этом `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Возвращает значение, представляющее количество часов в текущий день (–23 до 23).|  
|[CTimeSpan::GetMinutes](#getminutes)|Возвращает значение, представляющее количество минут в течение текущего часа (–59 до 59).|  
|[CTimeSpan::GetSeconds](#getseconds)|Возвращает значение, представляющее число секунд в текущей минуте (–59 до 59).|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Возвращает значение `CTimeSpan` объекта.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Возвращает значение, представляющее общее количество часов, полный в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает значение, представляющее общее число минут завершения в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает значение, представляющее общее число полный секунд в этом `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Выполняет сериализацию данных или из архива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор +.](#operator_add_-)|Добавление и вычитание `CTimeSpan` объектов.|  
|[оператор += – =](#operator_add_eq_-_eq)|Добавление и вычитание `CTimeSpan` и обратно это `CTimeSpan`.|  
|[оператор ==<>](#ctimespan_comparison_operators)|Сравнивает два значения относительного времени.|  
  
## <a name="remarks"></a>Примечания  
 `CTimeSpan`не имеет базового класса.  
  
 `CTimeSpan`функции преобразования в секундах различные комбинации дней, часов, минут и секунд.  
  
 `CTimeSpan` Объект хранится в **__time64_t** структуры, которая является 8 байт.  
  
 Вспомогательный класс, [CTime](../../atl-mfc-shared/reference/ctime-class.md), представляет абсолютное время.  
  
 `CTime` И `CTimeSpan` классы не предназначены для наследования. Поскольку нет виртуальных функций, размер и `CTime` и `CTimeSpan` объектов имеет ровно 8 байт. Большинство функций-членов приведены в коде.  
  
 Дополнительные сведения об использовании `CTimeSpan`, см. в статьях [даты и времени](../../atl-mfc-shared/date-and-time.md), и [управление временем](../../c-runtime-library/time-management.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>Операторы сравнения CTimeSpan  
 Операторы сравнения.  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
  
 Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эти операторы сравнения относительного времени. Они возвращают **true** Если условие имеет значение true; в противном случае **false**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#169;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 Создает `CTimeSpan` объекты различными способами.  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *timeSpanSrc*  
 Объект `CTimeSpan` объект, который уже существует.  
  
 `time`  
 Объект **__time64_t** значения времени число секунд в промежутке времени. В Visual C++ версии 6.0 и более ранних версиях `time` был значение `time_t`. Visual C++ .NET или позже, автоматически преобразует `time_t` параметр **__time64_t**.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Дни, часы минуты и секунды, соответственно.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создайте новый `CTimeSpan` инициализированный указанного относительного времени. Каждый конструктор описан ниже.  
  
- **(CTimeSpan); ** Создает неинициализированный объект `CTimeSpan` объект.  
  
- **CTimeSpan (const CTimeSpan &); ** Создает `CTimeSpan` из другого объекта `CTimeSpan` значение.  
  
- **CTimeSpan (__time64_t); ** Создает `CTimeSpan` объекта из **__time64_t** типа.  
  
- **CTimeSpan (LONG**, **int, int, int);** Создает `CTimeSpan` объекта из компонентов с каждым компонентом ограничен следующими диапазонами:  
  
    |Компонент|Диапазон|  
    |---------------|-----------|  
    |`lDays`|0 —&25;&000; (приблизительно)|  
    |`nHours`|0–23|  
    |`nMins`|0–59|  
    |`nSecs`|0–59|  
  
 Обратите внимание, что отладочная версия библиотеки классов Microsoft Foundation утверждает, если один или несколько компонентов времени суток выходит за пределы диапазона. Это необходимо проверить аргументы до вызова метода.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#162;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 Создает форматированную строку, соответствующий этому `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pFormat`, `pszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Форматирование кодов, ставится в процентах ( `%`) выполните вход, заменен соответствующим `CTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для **формат** перечислены ниже:  
  
- **%D** общее число дней в этом`CTimeSpan`  
  
- **%H** часов в текущий день  
  
- **Один** минут в течение текущего часа  
  
- **%S** секунды в текущей минуте  
  
- **%%**Знак процента  
  
 `nID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Отладочная версия библиотеки проверяет коды форматирования и утверждает, если код не выше в списке.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#163;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 Возвращает значение, представляющее число завершения дней в этом `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число дней, полный 24-часовой в промежутке времени. Это значение может быть отрицательным, если отрицательный интервал времени.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что может привести к летнее время `GetDays` для возврата потенциально неожиданных результатов. Например, после перехода на летнее время действует, **GetDays** сообщает число дней между 1 апреля и 1 мая как 29, 30 не, из-за один день в апреле сокращается на один час и поэтому не учитываются при подсчете полный день.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#164;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 Возвращает значение, представляющее количество часов в текущий день (–23 до 23).  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество часов в текущий день. Диапазон — от –23 до 23.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#165;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 Возвращает значение, представляющее количество минут в течение текущего часа (–59 до 59).  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество минут в текущий час. Диапазон — от –59 до 59.  
  
### <a name="example"></a>Пример  
 В примере показано [GetHours](#gethours).  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 Возвращает значение, представляющее число секунд в текущей минуте (–59 до 59).  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество секунд в текущей минуте. Диапазон — от –59 до 59.  
  
### <a name="example"></a>Пример  
 В примере показано [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Возвращает значение `CTimeSpan` объекта.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее значение `CTimeSpan` объекта.  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Возвращает значение, представляющее общее количество часов, полный в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество часов завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#166;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Возвращает значение, представляющее общее число минут завершения в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество минут для завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 В примере показано [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Возвращает значение, представляющее общее число полный секунд в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее число секунд для завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 В примере показано [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Добавление и вычитание `CTimeSpan` объектов.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Значение для добавления `CTimeSpan` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CTimeSpan` объект, представляющий результат операции.  
  
### <a name="remarks"></a>Примечания  
 Эти два оператора позволяют сложения и вычитания `CTimeSpan` объектов друг от друга.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&167;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=-=  
 Добавление и вычитание `CTimeSpan` и обратно это `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Значение для добавления `CTimeSpan` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `CTimeSpan` и обратно это `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities&#168;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
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
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




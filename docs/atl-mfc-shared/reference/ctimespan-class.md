---
title: "Класс CTimeSpan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cedf05bd8f5af198569891b4d6d59610d5098eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ctimespan-class"></a>Класс CTimeSpan
Количество времени, которое хранится внутренне как количество секунд в промежутке времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Создает `CTimeSpan` объекты различными способами.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Преобразует `CTimeSpan` в форматированную строку.|  
|[CTimeSpan::GetDays](#getdays)|Возвращает значение, представляющее количество завершения дней в этом `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Возвращает значение, представляющее количество часов в текущий день (от-23 до 23).|  
|[CTimeSpan::GetMinutes](#getminutes)|Возвращает значение, представляющее количество минут в течение текущего часа (-59 до 59).|  
|[CTimeSpan::GetSeconds](#getseconds)|Возвращает значение, представляющее количество секунд в текущей минуты (от -59 до 59).|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Возвращает значение `CTimeSpan` объекта.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Возвращает значение, представляющее общее количество завершения часов в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает значение, представляющее общее количество минут завершения в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает значение, представляющее общее число завершения секунд в этом `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Выполняет сериализацию данных в и из архива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор + -](#operator_add_-)|Добавляет и вычитает `CTimeSpan` объектов.|  
|[оператор +=-=](#operator_add_eq_-_eq)|Добавляет и вычитает `CTimeSpan` и обратно это `CTimeSpan`.|  
|[оператор == < и т. д.](#ctimespan_comparison_operators)|Сравнивает два значения относительного времени.|  
  
## <a name="remarks"></a>Примечания  
 `CTimeSpan`не имеет базового класса.  
  
 `CTimeSpan`функции преобразования в секундах различные комбинации дней, часов, минут и секунд.  
  
 `CTimeSpan` Объект сохраняется в **__time64_t** структуру, которая имеет размер 8 байт.  
  
 Вспомогательный класс, [CTime](../../atl-mfc-shared/reference/ctime-class.md), представляет абсолютное время.  
  
 `CTime` И `CTimeSpan` классы не предназначены для наследования. Так как нет виртуальных функций, размер и `CTime` и `CTimeSpan` объекты — ровно 8 байт. Большинство функций — членов приведены в коде.  
  
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
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
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
 Объект **__time64_t** значение времени, которое является количество секунд в промежутке времени.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Дни, часы минуты и секунды, соответственно.  
  
### <a name="remarks"></a>Примечания  
 Эти конструкторы создайте новый `CTimeSpan` инициализированный заданным временем относительный. Каждый конструктор описан ниже.  
  
- **(CTimeSpan);**  Создает неинициализированный `CTimeSpan` объекта.  
  
- **CTimeSpan (const CTimeSpan &);**  Создает `CTimeSpan` объекта из другого `CTimeSpan` значение.  
  
- **CTimeSpan (__time64_t);**  Создает `CTimeSpan` объекта из **__time64_t** типа.  
  
- **CTimeSpan (LONG**, **int, int, int);** Создает `CTimeSpan` объекта из компонентов с каждым компонентом ограничен следующих диапазонах:  
  
    |Компонент|Диапазон|  
    |---------------|-----------|  
    |`lDays`|0-25 000 (приблизительно)|  
    |`nHours`|0-23|  
    |`nMins`|0-59|  
    |`nSecs`|0-59|  
  
 Обратите внимание, что подтверждает отладочной версии библиотеки классов Microsoft Foundation, если один или несколько компонентов времени суток находится вне диапазона. Это необходимо проверить аргументы до вызова метода.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 Создает строку форматирования, которая соответствует этому `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Параметры  
 `pFormat`, `pszFormat`  
 Форматирование строки аналогично `printf` строка форматирования. Коды, предшествует процента форматирования ( `%`) выполните вход, заменен соответствующим `CTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для **формат** , перечислены ниже:  
  
- **%D** общее число дней, в этом`CTimeSpan`  
  
- **%H** часов в текущий день  
  
- **%M** минут в течение текущего часа  
  
- **%S** секунд в текущую минуту  
  
- **%%**Знак процента  
  
 `nID`  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Отладочная версия библиотеки проверяет коды форматирования и утверждения, если код не находится в списке выше.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 Возвращает значение, представляющее количество завершения дней в этом `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество дней, полный 24-часовом в промежутке времени. Это значение может быть отрицательным, если интервал времени является отрицательным значением.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что может привести к летнее время `GetDays` для возврата потенциально интересный результат. Например, при летнее время — фактически **GetDays** сообщает число дней между 1 апреля и 1 мая как 29, 30 не, так как один день в апреле сокращается на один час и поэтому не учитывается как полный день.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 Возвращает значение, представляющее количество часов в текущий день (от-23 до 23).  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество часов в текущий день. Диапазон — от-23 до 23.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 Возвращает значение, представляющее количество минут в течение текущего часа (-59 до 59).  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество минут в текущий час. Диапазон — от -59 до 59.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHours](#gethours).  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 Возвращает значение, представляющее количество секунд в текущей минуты (от -59 до 59).  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество секунд в текущей минуте. Диапазон — от -59 до 59.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Возвращает значение `CTimeSpan` объекта.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее значение `CTimeSpan` объекта.  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Возвращает значение, представляющее общее количество завершения часов в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество завершения часов в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Возвращает значение, представляющее общее количество минут завершения в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество минут для завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Возвращает значение, представляющее общее число завершения секунд в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество секунд для завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Добавляет и вычитает `CTimeSpan` объектов.  
  
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
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=-=  
 Добавляет и вычитает `CTimeSpan` и обратно это `CTimeSpan`.  
  
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
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
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
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)



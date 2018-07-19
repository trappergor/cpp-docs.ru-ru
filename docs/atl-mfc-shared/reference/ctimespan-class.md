---
title: Класс CTimeSpan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30b110e9c9f737f8dbbe46782613ca80240fb943
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880434"
---
# <a name="ctimespan-class"></a>Класс CTimeSpan
Количество времени, который хранится внутренним образом как количество секунд в промежутке времени.  
  
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
|[CTimeSpan::GetDays](#getdays)|Возвращает значение, представляющее число дней завершения в этом `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Возвращает значение, представляющее количество часов в текущий день (от -23 до 23).|  
|[CTimeSpan::GetMinutes](#getminutes)|Возвращает значение, представляющее количество минут в текущий час (от-59 до 59).|  
|[CTimeSpan::GetSeconds](#getseconds)|Возвращает значение, представляющее количество секунд в текущую минуту (от-59 до 59).|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Возвращает значение `CTimeSpan` объекта.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Возвращает значение, представляющее общее число полный часов в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Возвращает значение, представляющее общее число полный минут в этом `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Возвращает значение, представляющее общее число полный секунд в этом `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Сериализует данные из архива.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор + -](#operator_add_-)|Добавляет и вычитает `CTimeSpan` объектов.|  
|[оператор +=-=](#operator_add_eq_-_eq)|Добавляет и вычитает `CTimeSpan` и обратно это `CTimeSpan`.|  
|[оператор == < д.](#ctimespan_comparison_operators)|Сравнивает два значения относительного времени.|  
  
## <a name="remarks"></a>Примечания  
 `CTimeSpan` не имеет базового класса.  
  
 `CTimeSpan` преобразуют время в секундах различные комбинации дней, часов, минут и секунд.  
  
 `CTimeSpan` Объект хранится в **__time64_t** структуру, которая имеет размер 8 байт.  
  
 Вспомогательный класс, [CTime](../../atl-mfc-shared/reference/ctime-class.md), представляет абсолютное время.  
  
 `CTime` И `CTimeSpan` классы не предназначены для наследования. Так как нет виртуальных функций, размер оба `CTime` и `CTimeSpan` объекты — ровно 8 байт. Большинство функций-членов приведены в коде.  
  
 Дополнительные сведения об использовании `CTimeSpan`, см. в статьях [даты и времени](../../atl-mfc-shared/date-and-time.md), и [управление временем](../../c-runtime-library/time-management.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>  Операторы сравнения CTimeSpan  
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
 *диапазон*  
  
 Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эти операторы сравнения относительного времени. Они возвращают значение TRUE, если условие равно true; в противном случае — значение FALSE.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan  
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
  
 *time*  
 Объект **__time64_t** значение времени, которое представляет число секунд в промежутке времени.  
  
 *lDays*, *nHours*, *nMins*, *nSecs*  
 Дни, часы минуты и секунды, соответственно.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создают новый `CTimeSpan` объектом, который инициализируется с помощью указанного относительного времени. Каждый конструктор описан ниже.  
  
- `CTimeSpan( );` Создает неинициализированный `CTimeSpan` объекта.  
  
- `CTimeSpan( const CTimeSpan& );` Создает `CTimeSpan` из другого объекта `CTimeSpan` значение.  
  
- `CTimeSpan( __time64_t );` Создает `CTimeSpan` объекта из **__time64_t** типа.  
  
- `CTimeSpan( LONG, int, int, int );` Создает `CTimeSpan` объект из компонентов с каждым компонентом ограничен следующие диапазоны:  
  
    |Компонент|Диапазон|  
    |---------------|-----------|  
    |*lDays*|0 – 25 000 (приблизительно)|  
    |*nHours*|0-23|  
    |*nMins*|0-59|  
    |*nSecs*|0-59|  
  
 Обратите внимание, что отладочную версию библиотеки Microsoft Foundation Class утверждает, если один или несколько компонентов времени суток выходит за пределы диапазона. Это необходимо проверить аргументы до вызова метода.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>  CTimeSpan::Format  
 Создает форматированную строку, соответствующий этому `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Параметры  
 *pFormat*, *pszFormat*  
 Форматирование строки аналогичную `printf` форматирования строки. Коды, предшествует процента форматирования (`%`) выполните вход, заменен соответствующим `CTimeSpan` компонента. Другие символы в строке формата копируются без изменений возвращаемой строки. Значение и значение коды форматирования для `Format` , перечислены ниже:  
  
- **%D** Итого дней в этом `CTimeSpan`  
  
- **%H** часов в текущей даты  
  
- **%M** минут в текущий час  
  
- **%S** секунд в текущую минуту  
  
- **%%** Знак процента  
  
 *nID*  
 Идентификатор строки, который определяет этот формат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий времени в формате.  
  
### <a name="remarks"></a>Примечания  
 Отладочная версия библиотеки проверяет коды форматирования и утверждает, если код не в списке выше.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>  CTimeSpan::GetDays  
 Возвращает значение, представляющее число дней завершения в этом `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число дней завершения 24-часовом в промежутке времени. Это значение может быть отрицательным, если интервал времени является отрицательным.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что может привести к летнее время `GetDays` для возврата потенциально странный результат. Например, когда переход на летнее время действует, `GetDays` сообщает число дней между 1 апреля по 1 мая 29, а не 30, так как один день в апреле сокращается на один час и поэтому не учитывается как полный день.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>  CTimeSpan::GetHours  
 Возвращает значение, представляющее количество часов в текущий день (от -23 до 23).  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество часов в текущий день. Диапазон — от -23 до 23.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>  CTimeSpan::GetMinutes  
 Возвращает значение, представляющее количество минут в текущий час (от-59 до 59).  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество минут в текущий час. Находится в диапазоне от-59 до 59.  
  
### <a name="example"></a>Пример  
 См. в примере [GetHours](#gethours).  
  
##  <a name="getseconds"></a>  CTimeSpan::GetSeconds  
 Возвращает значение, представляющее количество секунд в текущую минуту (от-59 до 59).  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество секунд в текущей минуте. Находится в диапазоне от-59 до 59.  
  
### <a name="example"></a>Пример  
 См. в примере [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan  
 Возвращает значение `CTimeSpan` объекта.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее значение `CTimeSpan` объекта.  
  
##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours  
 Возвращает значение, представляющее общее число полный часов в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество часов полный из данного `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes  
 Возвращает значение, представляющее общее число полный минут в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее количество минут для завершения в этом `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 См. в примере [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds  
 Возвращает значение, представляющее общее число полный секунд в этом `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает общее число секунд для завершения из данного `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 См. в примере [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>  CTimeSpan::operator +, -  
 Добавляет и вычитает `CTimeSpan` объектов.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *диапазон*  
 Значение, которое нужно добавить `CTimeSpan` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CTimeSpan` объект, представляющий результат операции.  
  
### <a name="remarks"></a>Примечания  
 Разрешить эти два оператора для сложения и вычитания `CTimeSpan` объектов друг от друга.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator +=-=  
 Добавляет и вычитает `CTimeSpan` и обратно это `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *диапазон*  
 Значение, которое нужно добавить `CTimeSpan` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обновленный `CTimeSpan` объекта.  
  
### <a name="remarks"></a>Примечания  
 Эти операторы позволяют сложения и вычитания `CTimeSpan` и обратно это `CTimeSpan`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>  CTimeSpan::Serialize64  
  
> [!NOTE]
>  Этот метод доступен только в проектах MFC.  
  
 Сериализует данные, связанные с переменной-члена или из архива.  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 *ar*  
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
 [Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)



---
title: "Класс CFileTime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CFileTime
- CFileTime
- ATL.CFileTime
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
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
ms.openlocfilehash: 5ff7abc32093691d230787e8eb2d859bb4e77428
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletime-class"></a>Класс CFileTime
Этот класс предоставляет методы для управления значений даты и времени, связанного с файлом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Вызовите этот статическую функцию, чтобы получить `CFileTime` , представляющий текущую системную дату и время.|  
|[CFileTime::GetTime](#gettime)|Этот метод вызывается для получения времени из `CFileTime` объекта.|  
|[CFileTime::LocalToUTC](#localtoutc)|Этот метод вызывается для преобразования местного времени во время файла, на основе по Гринвичу (UTC).|  
|[CFileTime::SetTime](#settime)|Вызовите этот метод, чтобы указать дату и время хранятся по `CFileTime` объекта.|  
|[CFileTime::UTCToLocal](#utctolocal)|Этот метод вызывается для преобразования времени в формате UTC (UTC) для местного времени.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Этот оператор используется для выполнения вычитания `CFileTime` или `CFileTimeSpan` объекта.|  
|[CFileTime::operator! =](#operator_neq)|Этот оператор сравнивает два `CFileTime` объектов на неравенство.|  
|[CFileTime::operator +](#operator_add)|Этот оператор используется для сложения объекта `CFileTimeSpan`.|  
|[CFileTime::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.|  
|[CFileTime::operator&lt;](#operator_lt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.|  
|[CFileTime::operator =](#operator_eq)|Оператор присваивания.|  
|[CFileTime::operator-=](#operator_-_eq)|Этот оператор используется для выполнения вычитания `CFileTimeSpan` объекта и присвойте ей результат на текущий объект.|  
|[CFileTime::operator ==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CFileTime` на равенство.|  
|[CFileTime::operator&gt;](#operator_gt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих один день.|  
|[CFileTime::Hour](#hour)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих один час.|  
|[CFileTime::Millisecond](#millisecond)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одной миллисекунды.|  
|[CFileTime::Minute](#minute)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одну минуту.|  
|[CFileTime::Second](#second)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одну секунду.|  
|[CFileTime::Week](#week)|Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одну неделю.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления значениями даты и времени, связанные с создания, доступа и изменения файлов. Методы и данные этого класса часто используются в сочетании с `CFileTimeSpan` объекты, которые работают со значениями относительного времени.  
  
 Значение даты и времени хранится как 64-разрядное значение, представляющее количество 100-наносекундных интервалов с 1 января 1601 года. Это формат по Гринвичу (UTC).  
  
 Для упрощения расчетов предоставляются следующие статические константные переменные-члены:  
  
|Переменная-член|Число 100-наносекундных интервалов|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|Миллисекунды * 1000|  
|Minute|Второй * 60|  
|Hour|Мин * 60|  
|Day|Час * 24|  
|Неделя|День * 7|  
  
 **Примечание** не все файловые системы могут записывать создания и время последнего доступа и не все файловые системы запись их таким же образом. Для создания примера в файловой системе FAT Windows NT времени разрешением 10 миллисекунд, времени записи разрешением 2 секунды и время доступа разрешением 1 день (дата доступа). В файловой системе NTFS время доступа имеет разрешения 1 час. Кроме того FAT записывает время на диск в формате местного времени, но NTFS записывает время на диск в формате UTC. Дополнительные сведения см. в разделе [время файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="a-namecfiletimea--cfiletimecfiletime"></a><a name="cfiletime"></a>CFileTime::CFileTime  
 Конструктор.  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Объект [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуры.  
  
 `nTime`  
 Дата и время, выраженное как 64-разрядное значение.  
  
### <a name="remarks"></a>Примечания  
 `CFileTime` Объект может быть создан с помощью существующих даты и времени из `FILETIME` структуры или выражается как 64-разрядное значение (в локальной или форматы времени по Гринвичу (UTC)). Конструктор по умолчанию устанавливает время равным 0.  
  
##  <a name="a-namedaya--cfiletimeday"></a><a name="day"></a>CFileTime::Day  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих один день.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namegetcurrenttimea--cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Вызовите этот статическую функцию, чтобы получить `CFileTime` , представляющий текущую системную дату и время.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущую системную дату и время в формате всемирного координированного времени (UTC).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#41;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="a-namegettimea--cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime  
 Этот метод вызывается для получения времени из `CFileTime` объекта.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дату и время в виде 64-разрядное число, которое может быть в формате всемирного координированного времени (UTC) или локальной.  
  
##  <a name="a-namehoura--cfiletimehour"></a><a name="hour"></a>CFileTime::Hour  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих один час.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namelocaltoutca--cfiletimelocaltoutc"></a><a name="localtoutc"></a>CFileTime::LocalToUTC  
 Этот метод вызывается для преобразования местного времени во время файла, на основе по Гринвичу (UTC).  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, содержащий время в формате UTC.  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="a-namemilliseconda--cfiletimemillisecond"></a><a name="millisecond"></a>CFileTime::Millisecond  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одной миллисекунды.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#44;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="a-nameminutea--cfiletimeminute"></a><a name="minute"></a>CFileTime::Minute  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одну минуту.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-nameoperator-a--cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::operator-  
 Этот оператор используется для выполнения вычитания `CFileTime` или `CFileTimeSpan` объекта.  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
 `ft`  
 Объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объекта или `CFileTimeSpan` объект, представляющий результат разница во времени между двумя объектами.  
  
##  <a name="a-nameoperatorneqa--cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::operator! =  
 Этот оператор сравнивает два `CFileTime` объектов на неравенство.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равен `CFileTime` объекта, в противном случае **false**.  
  
##  <a name="a-nameoperatoradda--cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::operator +  
 Этот оператор используется для сложения объекта `CFileTimeSpan`.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, представляющий результат исходного времени и относительного времени.  
  
##  <a name="a-nameoperatoraddeqa--cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::operator +=  
 Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объект, представляющий результат исходного времени и относительного времени.  
  
##  <a name="a-nameoperatorlta--cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::operator&lt;  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (ранее вовремя) второй, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#43;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (ранее времени) или равен ему, в противном случае **false**.  
  
##  <a name="a-nameoperatoreqa--cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::operator =  
 Оператор присваивания.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Объект `CFileTime` объект, содержащий новое время и дата.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объекта.  
  
##  <a name="a-nameoperator-eqa--cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime::operator-=  
 Этот оператор используется для выполнения вычитания `CFileTimeSpan` объекта и присвойте ей результат на текущий объект.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan` объект, содержащий относительное время вычитается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объекта.  
  
##  <a name="a-nameoperatoreqeqa--cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::operator ==  
 Этот оператор сравнивает два объекта `CFileTime` на равенство.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 `CFileTime` Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны; в противном случае **false**.  
  
##  <a name="a-nameoperatorgta--cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::operator&gt;  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (позже по времени) второго, в противном случае **false**.  
  
##  <a name="a-nameoperatorgteqa--cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше (позже по времени) или равен ему, в противном случае **false**.  
  
##  <a name="a-nameseconda--cfiletimesecond"></a><a name="second"></a>CFileTime::Second  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих один день.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](#millisecond).  
  
##  <a name="a-namesettimea--cfiletimesettime"></a><a name="settime"></a>CFileTime::SetTime  
 Вызовите этот метод, чтобы указать дату и время хранятся по `CFileTime` объекта.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nTime`  
 64-разрядное значение, представляющее дату и время в формате всемирного координированного времени (UTC) или локального.  
  
##  <a name="a-nameutctolocala--cfiletimeutctolocal"></a><a name="utctolocal"></a>CFileTime::UTCToLocal  
 Этот метод вызывается для преобразования времени в формате UTC (UTC) для местного времени.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, содержащий время в формате времени локального файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#42;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="a-nameweeka--cfiletimeweek"></a><a name="week"></a>CFileTime::Week  
 Статические данные-член хранения количество 100-наносекундных интервалов, составляющих одну неделю.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [Класс CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




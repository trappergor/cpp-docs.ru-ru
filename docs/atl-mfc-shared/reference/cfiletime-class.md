---
title: "Класс CFileTime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
dev_langs:
- C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d48e899bb058ed27559a4ef699a3a53267064f98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfiletime-class"></a>Класс CFileTime
Этот класс предоставляет методы для управления значений даты и времени, связанного с файлом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|Вызовите эту статическую функцию для получения `CFileTime` объект, представляющий текущую системную дату и время.|  
|[CFileTime::GetTime](#gettime)|Этот метод вызывается для получения времени из `CFileTime` объекта.|  
|[CFileTime::LocalToUTC](#localtoutc)|Этот метод используется для преобразования местного времени во временную характеристику файла на основе по Гринвичу (UTC).|  
|[CFileTime::SetTime](#settime)|Вызовите этот метод, чтобы указать дату и время, хранящихся в `CFileTime` объекта.|  
|[CFileTime::UTCToLocal](#utctolocal)|Этот метод используется для преобразования времени по Гринвичу (UTC) для местного времени.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|Этот оператор используется для вычитания `CFileTime` или `CFileTimeSpan` объекта.|  
|[CFileTime::operator! =](#operator_neq)|Этот оператор сравнивает два `CFileTime` объектов на неравенство.|  
|[CFileTime::operator +](#operator_add)|Этот оператор используется для сложения объекта `CFileTimeSpan`.|  
|[CFileTime::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.|  
|[CFileTime::operator&lt;](#operator_lt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.|  
|[CFileTime::operator =](#operator_eq)|Оператор присваивания.|  
|[CFileTime::operator-=](#operator_-_eq)|Этот оператор используется для вычитания `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|  
|[CFileTime::operator ==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CFileTime` на равенство.|  
|[CFileTime::operator&gt;](#operator_gt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[CFileTime::Day](#day)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.|  
|[CFileTime::Hour](#hour)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих один час.|  
|[CFileTime::Millisecond](#millisecond)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих до одной миллисекунды.|  
|[CFileTime::Minute](#minute)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну минуту.|  
|[CFileTime::Second](#second)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну секунду.|  
|[CFileTime::Week](#week)|Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну неделю.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления значениями даты и времени, связанные с создания, доступа и изменения файлов. Методы и данные этого класса часто используются в сочетании с `CFileTimeSpan` объекты, которые работают со значениями относительного времени.  
  
 Значение даты и времени сохраняется как 64-разрядное значение, представляющее количество 100-наносекундных интервалов с 1 января 1601 года. Это формат по Гринвичу (UTC).  
  
 Для упрощения расчетов предусмотрены следующие статические константные переменные-члены.  
  
|Переменная-член|Число 100-наносекундных интервалов|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|Миллисекунды * 1000|  
|Minute|Второй * 60|  
|Hour|Мин * 60|  
|Day|Час * 24|  
|Неделя|День * 7|  
  
 **Примечание** не все файловые системы могут записывать создания и время последнего доступа и не все файловые системы запись их таким же образом. Для примера, в файловой системе FAT Windows NT, создайте времени с разрешением 10 миллисекунд, время записи с разрешением 2 секунды и время доступа с разрешением 1 день (дату доступа). В файловой системе NTFS время доступа с разрешением 1 час. Кроме того FAT записывает время на диск в формате местного времени, но NTFS записывает время на диск в формате UTC. Дополнительные сведения см. в разделе [времени файлов](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="cfiletime"></a>CFileTime::CFileTime  
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
 `CFileTime` Объект может быть создан с помощью существующего даты и времени из `FILETIME` структуры или выражается как 64-разрядное значение (в локальной или форматов времени по Гринвичу (UTC)). Конструктор по умолчанию устанавливает время в 0.  
  
##  <a name="day"></a>CFileTime::Day  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](#millisecond).  
  
##  <a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 Вызовите эту статическую функцию для получения `CFileTime` объект, представляющий текущую системную дату и время.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущую системную дату и время в формате общего скоординированного времени (UTC).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="gettime"></a>CFileTime::GetTime  
 Этот метод вызывается для получения времени из `CFileTime` объекта.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дату и время в виде 64-разрядное число, которое может быть в формате локальной или по Гринвичу (UTC).  
  
##  <a name="hour"></a>CFileTime::Hour  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих один час.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](#millisecond).  
  
##  <a name="localtoutc"></a>CFileTime::LocalToUTC  
 Этот метод используется для преобразования местного времени во временную характеристику файла на основе по Гринвичу (UTC).  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, содержащий время в формате UTC.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::UTCToLocal](#utctolocal).  
  
##  <a name="millisecond"></a>CFileTime::Millisecond  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих до одной миллисекунды.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="minute"></a>CFileTime::Minute  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну минуту.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](#millisecond).  
  
##  <a name="operator_-"></a>CFileTime::operator-  
 Этот оператор используется для вычитания `CFileTime` или `CFileTimeSpan` объекта.  
  
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
 Возвращает `CFileTime` объекта или `CFileTimeSpan` объект, представляющий результат разницы во времени между двумя объектами.  
  
##  <a name="operator_neq"></a>CFileTime::operator! =  
 Этот оператор сравнивает два `CFileTime` объектов на неравенство.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равно `CFileTime` объекта, в противном случае **false**.  
  
##  <a name="operator_add"></a>CFileTime::operator +  
 Этот оператор используется для сложения объекта `CFileTimeSpan`.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, представляющий результат исходного времени и относительного времени.  
  
##  <a name="operator_add_eq"></a>CFileTime::operator +=  
 Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объект, представляющий результат исходного времени и относительного времени.  
  
##  <a name="operator_lt"></a>CFileTime::operator&lt;  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (ранее во времени), второй **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше, чем (ранее времени) или равно значению второго, в противном случае **false**.  
  
##  <a name="operator_eq"></a>CFileTime::operator =  
 Оператор присваивания.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Объект `CFileTime` объект, содержащий новое время и дату.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объекта.  
  
##  <a name="operator_-_eq"></a>CFileTime::operator-=  
 Этот оператор используется для вычитания `CFileTimeSpan` объекта и присвоить его результат в текущий объект.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan` объект, содержащий относительного времени для вычитания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTime` объекта.  
  
##  <a name="operator_eq_eq"></a>CFileTime::operator ==  
 Этот оператор сравнивает два объекта `CFileTime` на равенство.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 `CFileTime` Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны; в противном случае **false**.  
  
##  <a name="operator_gt"></a>CFileTime::operator&gt;  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (позже по времени) второго, в противном случае **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ft`  
 Сравниваемый объект `CFileTime`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше (позже по времени) или равно значению второго, в противном случае **false**.  
  
##  <a name="second"></a>CFileTime::Second  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих один день.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](#millisecond).  
  
##  <a name="settime"></a>CFileTime::SetTime  
 Вызовите этот метод, чтобы указать дату и время, хранящихся в `CFileTime` объекта.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nTime`  
 64-разрядное значение, представляющее дату и время в формате локальной или по Гринвичу (UTC).  
  
##  <a name="utctolocal"></a>CFileTime::UTCToLocal  
 Этот метод используется для преобразования времени по Гринвичу (UTC) для местного времени.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTime` объект, содержащий время в формате времени локального файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="week"></a>CFileTime::Week  
 Статические данные-член хранить число 100-наносекундных интервалов, составляющих одну неделю.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](#millisecond).  
  
## <a name="see-also"></a>См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [Класс CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)



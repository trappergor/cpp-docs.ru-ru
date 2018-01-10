---
title: "Класс CFileTimeSpan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs: C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da47f0113ec2e36f6df4afa32f6aff84d5ee6dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfiletimespan-class"></a>Класс CFileTimeSpan
Этот класс предоставляет методы для управления относительной даты и значения времени, связанного с файлом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Этот метод вызывается для получения промежутка времени из `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Вызовите этот метод, чтобы задать период времени `CFileTimeSpan` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Выполняет вычитание `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::operator! =](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|  
|[CFileTimeSpan::operator +](#operator_add)|Выполняет действие на `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Выполняет действие на `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|Сравнивает два `CFileTimeSpan` объектами, чтобы определить меньший из них.|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|Сравнивает два `CFileTimeSpan` объектами, чтобы определить равенство или меньший из них.|  
|[CFileTimeSpan::operator =](#operator_eq)|Оператор присваивания.|  
|[CFileTimeSpan::operator-=](#operator_-_eq)|Выполняет вычитание `CFileTimeSpan` объекта и присвоить его результат в текущий объект.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|Сравнивает два `CFileTimeSpan` объектами, чтобы определить большее.|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|Сравнивает два `CFileTimeSpan` объектами, чтобы определить равенство или больший.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления относительный периоды времени, часто встречающихся при выполнении операций, определяя время была создана, последнего обращения к или последнего изменения файла. Методы этого класса часто используются в сочетании с [CFileTime класс](../../atl-mfc-shared/reference/cfiletime-class.md) объектов.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
 Конструктор.  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Существующий объект `CFileTimeSpan`.  
  
 `nSpan`  
 Период времени в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 `CFileTimeSpan` Объект может быть создан с помощью существующей `CFileTimeSpan` объекта или выражается как 64-разрядное значение. Конструктор по умолчанию задает промежуток времени, равным 0.  
  
##  <a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 Этот метод вызывается для получения промежутка времени из `CFileTimeSpan` объекта.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает интервал времени в миллисекундах.  
  
##  <a name="operator_-"></a>CFileTimeSpan::operator-  
 Выполняет вычитание **CFileTimeSpan** объекта.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTimeSpan` объект, представляющий результат разницу между двумя промежутками времени.  
  
##  <a name="operator_neq"></a>CFileTimeSpan::operator! =  
 Проверяет неравенство двух объектов `CFileTimeSpan`.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равно `CFileTimeSpan` объекта; в противном случае **false**.  
  
##  <a name="operator_add"></a>CFileTimeSpan::operator +  
 Выполняет действие на `CFileTimeSpan` объекта.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.  
  
##  <a name="operator_add_eq"></a>CFileTimeSpan::operator +=  
 Выполняет действие на `CFileTimeSpan` объекта и присваивает результат в текущий объект.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.  
  
##  <a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 Сравнивает два `CFileTimeSpan` объектами, чтобы определить меньший из них.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (то есть представляет короткий период времени) второго, в противном случае **false**.  
  
##  <a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 Сравнивает два `CFileTimeSpan` объектами, чтобы определить равенство или меньший из них.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (то есть представляет короткий период времени) меньше второго, в противном случае **false**.  
  
##  <a name="operator_eq"></a>CFileTimeSpan::operator =  
 Оператор присваивания.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объекта.  
  
##  <a name="operator_-_eq"></a>CFileTimeSpan::operator-=  
 Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат в текущий объект.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объекта.  
  
##  <a name="operator_eq_eq"></a>CFileTimeSpan::operator ==  
 Сравнивает два объекта `CFileTimeSpan` на равенство.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны; в противном случае **false**.  
  
##  <a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 Сравнивает два `CFileTimeSpan` объектами, чтобы определить большее.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (то есть представляет периода) второго, в противном случае **false**.  
  
##  <a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 Сравнивает два `CFileTimeSpan` объектами, чтобы определить равенство или больший.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (то есть представляет периода) меньше второго, в противном случае **false**.  
  
##  <a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 Вызовите этот метод, чтобы задать период времени `CFileTimeSpan` объекта.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nSpan`  
 Новое значение для диапазона времени в миллисекундах.  
  
## <a name="see-also"></a>См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [Класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)



---
title: "Класс CFileTimeSpan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATL.CFileTimeSpan
- ATL::CFileTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
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
ms.openlocfilehash: 8a25bab65d9e5705a71eddde901e747c43a5a002
ms.lasthandoff: 02/24/2017

---
# <a name="cfiletimespan-class"></a>Класс CFileTimeSpan
Этот класс предоставляет методы для управления относительных значений даты и времени связанного с файлом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Этот метод вызывается для получения интервал времени из `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Вызовите этот метод, чтобы задать период `CFileTimeSpan` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|Выполняет вычитание `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::operator! =](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|  
|[CFileTimeSpan::operator +](#operator_add)|Выполняет сложение `CFileTimeSpan` объекта.|  
|[CFileTimeSpan::operator +=](#operator_add_eq)|Выполняет сложение `CFileTimeSpan` объекта и присвойте ей результат на текущий объект.|  
|[CFileTimeSpan::operator&lt;](#operator_lt)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить меньшее значение.|  
|[CFileTimeSpan::operator&lt;=](#operator_lt_eq)|Сравнивает два `CFileTimeSpan` объектов для определения равенства или меньшее значение.|  
|[CFileTimeSpan::operator =](#operator_eq)|Оператор присваивания.|  
|[CFileTimeSpan::operator-=](#operator_-_eq)|Выполняет вычитание `CFileTimeSpan` объекта и присвойте ей результат на текущий объект.|  
|[CFileTimeSpan::operator ==](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|  
|[CFileTimeSpan::operator&gt;](#operator_gt)|Сравнивает два `CFileTimeSpan` объектов, чтобы определить большее.|  
|[CFileTimeSpan::operator&gt;=](#operator_gt_eq)|Сравнивает два `CFileTimeSpan` объектов для определения равенства или большее.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для управления относительный периодов времени, часто встречающихся при выполнении операций, определяя время создания, последнего доступа к или файла последнего изменения. Методы этого класса часто используются в сочетании с [CFileTime класс](../../atl-mfc-shared/reference/cfiletime-class.md) объектов.  
  
## <a name="example"></a>Пример  
 В примере показано [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atltime.h  
  
##  <a name="a-namecfiletimespana--cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan  
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
 `CFileTimeSpan` Объект может быть создан с помощью существующего `CFileTimeSpan` объекта или выражается как 64-разрядное значение. Конструктор по умолчанию задает интервал времени, равным 0.  
  
##  <a name="a-namegettimespana--cfiletimespangettimespan"></a><a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan  
 Этот метод вызывается для получения интервал времени из `CFileTimeSpan` объекта.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает интервал времени в миллисекундах.  
  
##  <a name="a-nameoperator-a--cfiletimespanoperator--"></a><a name="operator_-"></a>CFileTimeSpan::operator-  
 Выполняет вычитание **CFileTimeSpan** объекта.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTimeSpan` объект, представляющий результат разницу между двумя промежутками времени.  
  
##  <a name="a-nameoperatorneqa--cfiletimespanoperator-"></a><a name="operator_neq"></a>CFileTimeSpan::operator! =  
 Проверяет неравенство двух объектов `CFileTimeSpan`.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равен `CFileTimeSpan` объекта; в противном случае **false**.  
  
##  <a name="a-nameoperatoradda--cfiletimespanoperator-"></a><a name="operator_add"></a>CFileTimeSpan::operator +  
 Выполняет сложение `CFileTimeSpan` объекта.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.  
  
##  <a name="a-nameoperatoraddeqa--cfiletimespanoperator-"></a><a name="operator_add_eq"></a>CFileTimeSpan::operator +=  
 Выполняет сложение на `CFileTimeSpan` объект и присваивает результат на текущий объект.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объект, содержащий сумму два временных диапазонов.  
  
##  <a name="a-nameoperatorlta--cfiletimespanoperator-lt"></a><a name="operator_lt"></a>CFileTimeSpan::operator&lt;  
 Сравнивает два `CFileTimeSpan` объектов, чтобы определить меньшее значение.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше (то есть, представляет более короткий период времени) второго, в противном случае **false**.  
  
##  <a name="a-nameoperatorlteqa--cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>CFileTimeSpan::operator&lt;=  
 Сравнивает два `CFileTimeSpan` объектов для определения равенства или меньшее значение.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше, чем (то есть, представляет более короткий период времени) или равен второму, в противном случае **false**.  
  
##  <a name="a-nameoperatoreqa--cfiletimespanoperator-"></a><a name="operator_eq"></a>CFileTimeSpan::operator =  
 Оператор присваивания.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объекта.  
  
##  <a name="a-nameoperator-eqa--cfiletimespanoperator--"></a><a name="operator_-_eq"></a>CFileTimeSpan::operator-=  
 Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат на текущий объект.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CFileTimeSpan` объекта.  
  
##  <a name="a-nameoperatoreqeqa--cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>CFileTimeSpan::operator ==  
 Сравнивает два объекта `CFileTimeSpan` на равенство.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны; в противном случае **false**.  
  
##  <a name="a-nameoperatorgta--cfiletimespanoperator-gt"></a><a name="operator_gt"></a>CFileTimeSpan::operator&gt;  
 Сравнивает два `CFileTimeSpan` объектов, чтобы определить большее.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (то есть, представляет длительного периода времени) второго, в противном случае **false**.  
  
##  <a name="a-nameoperatorgteqa--cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>CFileTimeSpan::operator&gt;=  
 Сравнивает два `CFileTimeSpan` объектов для определения равенства или большее.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `span`  
 Сравниваемый объект `CFileTimeSpan`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше, чем (то есть, представляет длительного периода времени) или равен второму, в противном случае **false**.  
  
##  <a name="a-namesettimespana--cfiletimespansettimespan"></a><a name="settimespan"></a>CFileTimeSpan::SetTimeSpan  
 Вызовите этот метод, чтобы задать период `CFileTimeSpan` объекта.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nSpan`  
 Новое значение интервал времени в миллисекундах.  
  
## <a name="see-also"></a>См. также  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [Класс CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)




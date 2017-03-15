---
title: "Класс Location | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::location
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1a404f44600addcbf332fabcfc19a7b48dab0c81
ms.lasthandoff: 02/24/2017

---
# <a name="location-class"></a>Класс location
Абстракция физического расположения на оборудовании.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class location;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[расположение конструктор](#ctor)|Перегружен. Создает объект `location`.|  
|[~ расположение деструктор](#dtor)|Уничтожает объект `location`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[текущий метод](#current)|Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.|  
|[from_numa_node метод](#from_numa_node)|Возвращает объект `location`, представляющий заданный узел NUMA.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](#operator_neq)|Определяет, представляют ли два объекта `location` различные расположения.|  
|[оператор =-оператор](#operator_eq)|Назначает содержимое другого объекта `location` данному.|  
|[оператор ==-оператор](#operator_eq_eq)|Определяет неравенство двух `location` объекты представляют местоположения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `location`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-location"></a><a name="dtor"></a>~ расположение 

 Уничтожает объект `location`.  
  
```
~location();
```  
  
##  <a name="a-namecurrenta-current"></a><a name="current"></a>текущий 

 Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение, представляющее наиболее определенное место, выполняемое вызывающим потоком.  
  
##  <a name="a-namefromnumanodea-fromnumanode"></a><a name="from_numa_node"></a>from_numa_node 

 Возвращает объект `location`, представляющий заданный узел NUMA.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Параметры  
 `_NumaNodeNumber`  
 Номер узла NUMA для построения его расположения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение, представляющее узел NUMA, указывается с помощью параметра `_NumaNodeNumber`.  
  
##  <a name="a-namectora-location"></a><a name="ctor"></a>расположение 

 Создает объект `location`.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>Примечания  
 Созданное расположение по умолчанию представляет систему в целом.  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>оператор! = 

 Определяет, представляют ли два объекта `location` различные расположения.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если расположения различаются; в противном случае — значение `false`.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

 Назначает содержимое другого объекта `location` данному.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
 Исходный объект `location`.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>оператор == 

 Определяет неравенство двух `location` объекты представляют местоположения.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если в двух местах идентичны, и `false` в противном случае.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)


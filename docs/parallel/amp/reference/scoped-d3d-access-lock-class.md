---
title: "Класс scoped_d3d_access_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
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
ms.openlocfilehash: c5bc6183b3abc7a5598159717b0dbfa1dae2a05d
ms.lasthandoff: 02/24/2017

---
# <a name="scopedd3daccesslock-class"></a>Класс scoped_d3d_access_lock
Программа-оболочка RAII блокировку доступа D3D accelerator_view объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор scoped_d3d_access_lock](#ctor)|Перегружен. Создает объект `scoped_d3d_access_lock`. Блокировка снимается, когда этот объект выходит из области.|  
|[~ Деструктор scoped_d3d_access_lock](#dtor)|Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор =-оператор](#operator_eq)|Получает право на владение блокировки из другого `scoped_d3d_access_lock`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** concurrency::direct3d  

##  <a name="a-namectora-scopedd3daccesslock"></a><a name="ctor"></a>scoped_d3d_access_lock 

 Создает объект `scoped_d3d_access_lock`. Блокировка снимается, когда этот объект выходит из области.  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 `accelerator_view` Применять блокировки.  
  
 `_T`  
 Объект `adopt_d3d_access_lock_t`.  
  
 `_Other`  
 `scoped_d3d_access_lock` Объект, из которого требуется переместить существующей блокировки.  
  
## <a name="construction"></a>Создание  
 [1] конструктор  
 Получает блокировку доступа D3D на данной [accelerator_view](accelerator-view-class.md) объекта. Построение блокируется до блокировки.  
  
 [2] конструктор  
 Применять блокировку доступа D3D из данного [accelerator_view](accelerator-view-class.md) объекта.  
  
 [3] конструктор перемещения  
 Использует существующую D3D блокировку доступа из другого `scoped_d3d_access_lock` объекта. Построение не блокируется.  

  
##  <a name="a-namedtora-scopedd3daccesslock"></a><a name="dtor"></a>~ scoped_d3d_access_lock 

 Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

Принимает владение блокировки D3D доступа из другого `scoped_d3d_access_lock` объекта, снятие блокировки предыдущей.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 Accelerator_view, из которого требуется переместить D3D блокировку доступа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `scoped_accelerator_view_lock`.  

## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Direct3D](concurrency-direct3d-namespace.md)


---
title: "Класс scoped_d3d_access_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a592249221129bce35f8592dcec56ff2379472d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="scopedd3daccesslock-class"></a>Класс scoped_d3d_access_lock
Оболочка RAII для блокировки доступа D3D accelerator_view объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[scoped_d3d_access_lock Constructor](#ctor)|Перегружен. Создает объект `scoped_d3d_access_lock`. Блокировка снимается в том случае, когда этот объект выходит из области.|  
|[~scoped_d3d_access_lock Destructor](#dtor)|Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Принимает право на владение блокировки из другого `scoped_d3d_access_lock`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Namespace:** concurrency::direct3d  

##  <a name="ctor"></a> scoped_d3d_access_lock 

 Создает объект `scoped_d3d_access_lock`. Блокировка снимается в том случае, когда этот объект выходит из области.  
 
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
 `accelerator_view` Блокировки перейти к использованию.  
  
 `_T`  
 Объект `adopt_d3d_access_lock_t`.  
  
 `_Other`  
 `scoped_d3d_access_lock` Объект, из которого для перемещения существующей блокировки.  
  
## <a name="construction"></a>Создание экземпляра  
 [1] конструктор  
 Получает блокировку доступа D3D на данной [accelerator_view](accelerator-view-class.md) объекта. Построение блокируется, если блокировка получена.  
  
 [2] конструктор  
 Применять блокировку доступа D3D из заданного [accelerator_view](accelerator-view-class.md) объекта.  
  
 [3] конструктор перемещения  
 Принимает существующей блокировки D3D доступа из другого `scoped_d3d_access_lock` объекта. Построение не блокируется.  

  
##  <a name="dtor"></a> ~scoped_d3d_access_lock 

 Освобождает блокировку доступа D3D в связанном `accelerator_view` объект.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a> оператор = 

Принимает право на владение D3D блокировку доступа из другого `scoped_d3d_access_lock` объекта, снятие блокировки предыдущей.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 Accelerator_view, из которого требуется переместить блокировки доступа D3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `scoped_accelerator_view_lock`.  

## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)

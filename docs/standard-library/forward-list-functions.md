---
title: "Функции &lt;forward_list&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b1c8cbb3a8dbbf7f6c14400f531e7ab40a2c84f6
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-functions"></a>Функции &lt;forward_list&gt;
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 Меняет местами элементы двух прямых списков.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект типа `forward_list`.|  
|`right`|Объект типа `forward_list`.|  
  
### <a name="remarks"></a>Примечания  
 Шаблонная функция выполняет `left.swap(right)`.  
  
## <a name="see-also"></a>См. также  
 [<forward_list>](../standard-library/forward-list.md)





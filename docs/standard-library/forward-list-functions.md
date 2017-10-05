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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 6696f42d2ba7cb6daabb8f2ff38093911838c1ca
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

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





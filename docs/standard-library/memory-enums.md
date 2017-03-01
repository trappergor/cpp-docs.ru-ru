---
title: "Перечисления &lt;memory&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9c3440495d77b788658cffefc917d9960ca1f833
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-enums"></a>Перечисления &lt;memory&gt;
||  
|-|  
|[Перечисление pointer_safety](#pointer_safety_enumeration)|  
  
##  <a name="a-namepointersafetyenumerationa--pointersafety-enumeration"></a><a name="pointer_safety_enumeration"></a>  Перечисление pointer_safety  
 Перечисление возможных значений, возвращаемых `get_pointer_safety`.  
  
class pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>Примечания  
 Ограниченное `enum` определяет значения, которые могут быть возвращены `get_pointer_safety``()`:  
  
 `relaxed` — указатели, наследованные небезопасно (указатели на объявленные объекты или объекты, для которых выделена память), обрабатываются так же, как наследованные безопасно.  
  
 `preferred` — как и раньше, но указатели, наследованные небезопасно, не должны разыменовываться.  
  
 `strict` — указатели, наследованные небезопасно, могут обрабатываться не так, как наследованные безопасно.  
  
## <a name="see-also"></a>См. также  
 [\<memory>](../standard-library/memory.md)





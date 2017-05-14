---
title: "Перечисления &lt;memory&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: d2f3cf1ec90c7caff5bb3a100d45d69a4a35e01a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltmemorygt-enums"></a>Перечисления &lt;memory&gt;
||  
|-|  
|[pointer_safety](#pointer_safety)|  
  
##  <a name="pointer_safety"></a>  Перечисление pointer_safety  
 Перечисление возможных значений, возвращаемых `get_pointer_safety`.  
  
class pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>Примечания  
 Ограниченное `enum` определяет значения, которые могут быть возвращены `get_pointer_safety``()`:  
  
 `relaxed` — указатели, наследованные небезопасно (указатели на объявленные объекты или объекты, для которых выделена память), обрабатываются так же, как наследованные безопасно.  
  
 `preferred` — как и раньше, но указатели, наследованные небезопасно, не должны разыменовываться.  
  
 `strict` — указатели, наследованные небезопасно, могут обрабатываться не так, как наследованные безопасно.  
  
## <a name="see-also"></a>См. также  
 [\<memory>](../standard-library/memory.md)





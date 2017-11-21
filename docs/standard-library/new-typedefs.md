---
title: "Определения типов &lt;new&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: e23ea06002dc840997a0e7202f581cd81ef407c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltnewgt-typedefs"></a>Определения типов &lt;new&gt;
||  
|-|  
|[new_handler](#new_handler)|  
  
##  <a name="new_handler"></a>  new_handler  
 Тип указывает на функцию, подходящую для использования в качестве нового обработчика.  
  
```
typedef void (*new_handler)();
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип функции обработчика вызывается **operator new** или `operator new[]`, если они не могут удовлетворить запрос на дополнительное хранилище.  
  
### <a name="example"></a>Пример  
  См. [set_new_handler](../standard-library/new-functions.md#set_new_handler) с примером использования `new_handler` в качестве как возвращаемого значения.  
  
## <a name="see-also"></a>См. также  
 [\<new>](../standard-library/new.md)




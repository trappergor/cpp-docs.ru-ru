---
title: "Определения типов &lt;system_error&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: feb6e7bcf5844f3533f93eb3aec5737ce9d3d784
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-typedefs"></a>Определения типов &lt;system_error&gt;
||  
|-|  
|[generic_errno](#generic_errno)|  
  
##  <a name="a-namegenericerrnoa--genericerrno"></a><a name="generic_errno"></a>  generic_errno  
 Тип, который представляет перечисление, предоставляющее символьные имена для всех макросов с ошибками в коде, определяемых Posix в `<errno.h>`.  
  
```
typedef errc generic_error;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом [errc](../standard-library/system-error-enums.md#errc_enumeration).  
  
## <a name="see-also"></a>См. также  
 [<system_error>](../standard-library/system-error.md)





---
title: "Определения типов &lt;system_error&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: c54540d9a883acc7e0374878f354b1a3fdb3953f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltsystemerrorgt-typedefs"></a>Определения типов &lt;system_error&gt;
||  
|-|  
|[generic_errno](#generic_errno)|  
  
##  <a name="generic_errno"></a>  generic_errno  
 Тип, который представляет перечисление, предоставляющее символьные имена для всех макросов с ошибками в коде, определяемых Posix в `<errno.h>`.  
  
```
typedef errc generic_error;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом [errc](../standard-library/system-error-enums.md#errc).  
  
## <a name="see-also"></a>См. также  
 [<system_error>](../standard-library/system-error.md)





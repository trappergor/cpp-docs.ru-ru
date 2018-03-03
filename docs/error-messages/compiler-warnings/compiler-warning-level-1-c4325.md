---
title: "Предупреждение (уровень 1) C4325 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4325"></a>Предупреждение компилятора (уровень 1) C4325
**атрибутов для стандартной секции "**   
 ***раздел* "игнорируется**  
  
 Не допускается изменение атрибутов стандартного раздела. Пример:  
  
```  
#pragma section(".sdata", long)  
```  
  
 Это привело бы к перезаписи `.sdata` стандартного раздела, который использует **короткие** тип данных с **длинные** тип данных.  
  
 Включает стандартные разделы, атрибуты которого не может быть изменен,  
  
-   .Data  
  
-   .sdata  
  
-   .BSS  
  
-   .SBSS  
  
-   .Text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Дополнительные разделы могут быть добавлены позже.  
  
## <a name="see-also"></a>См. также  
 [section](../../preprocessor/section.md)
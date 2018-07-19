---
title: Предупреждение (уровень 1) C4325 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936433987f823ae7d5d22cfd075f188dd5d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277648"
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
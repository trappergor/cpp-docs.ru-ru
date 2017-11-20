---
title: "CLOCKS_PER_SEC, CLK_TCK | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
dev_langs: C++
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: facd2469a4b95351d54addce663d0b036db38786
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC, CLK_TCK
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <time.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Время в секундах — значение, возвращаемое функцией `clock`, разделенное на `CLOCKS_PER_SEC`. `CLK_TCK` эквивалентно, но считается устаревшим.  
  
## <a name="see-also"></a>См. также  
 [clock](../c-runtime-library/reference/clock.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)
---
title: "_CRT_DISABLE_PERFCRIT_LOCKS | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs: C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb9a5662b15e6e4d0b6df09520263528f9fa72c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS
Отключает критическую с точки зрения производительности блокировку в операциях ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## <a name="remarks"></a>Примечания  
 Определение этого символа может улучшить производительность в однопоточных привязанных к вводу-выводу программах путем принудительного использования однопоточной модели ввода-вывода во всех операциях ввода-вывода. Подробнее см. [Производительность многопоточных библиотек](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## <a name="see-also"></a>См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)
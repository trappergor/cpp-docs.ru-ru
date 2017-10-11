---
title: "_CRTDBG_MAP_ALLOC | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a2b61b315baa337675147ded1232a943e82b24ec
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
Когда в отладочной версии приложения определен флаг **_CRTDBG_MAP_ALLOC**, базовые версии функций кучи напрямую сопоставляется с их отладочными версиями. Этот флаг используется в файле Crtdbg.h для выполнения сопоставления. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.  
  
 Дополнительные сведения об использовании отладочной и базовой версий функции кучи см. в разделе [Использование отладочной и базовой версий](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="see-also"></a>См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)

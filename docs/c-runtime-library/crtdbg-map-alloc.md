---
title: _CRTDBG_MAP_ALLOC | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 855b057223d7bdd69d7275e8c2acc0dd72bc256c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386483"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
Когда в отладочной версии приложения определен флаг **_CRTDBG_MAP_ALLOC**, базовые версии функций кучи напрямую сопоставляется с их отладочными версиями. Этот флаг используется в файле Crtdbg.h для выполнения сопоставления. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.  
  
 Дополнительные сведения об использовании отладочной и базовой версий функции кучи см. в разделе [Использование отладочной и базовой версий](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="see-also"></a>См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)
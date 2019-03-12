---
title: _CRTDBG_MAP_ALLOC
ms.date: 11/04/2016
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
ms.openlocfilehash: 8bcb0f5ea26218b74034eb0a41199a1104ba944d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739778"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC

Когда в отладочной версии приложения определен флаг **_CRTDBG_MAP_ALLOC**, базовые версии функций кучи напрямую сопоставляется с их отладочными версиями. Этот флаг используется в файле Crtdbg.h для выполнения сопоставления. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.

Дополнительные сведения об использовании отладочной и базовой версий функции кучи см. в разделе [Использование отладочной и базовой версий](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="see-also"></a>См. также

[Флаги управления](../c-runtime-library/control-flags.md)

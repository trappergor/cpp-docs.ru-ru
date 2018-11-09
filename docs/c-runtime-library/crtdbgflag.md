---
title: _crtDbgFlag
ms.date: 11/04/2016
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
ms.openlocfilehash: 5abb0418b5ffb1f95bf7b362f621f99f411094d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435299"
---
# <a name="crtdbgflag"></a>_crtDbgFlag

Флаг **_crtDbgFlag** состоит из пяти битовых полей, которые управляют отслеживанием, проверкой, созданием отчетов и созданием дампа для выделения памяти в отладочной версии кучи. Битовые поля флага задаются с помощью функции [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md). Этот флаг и его битовые поля объявляются в Crtdbg.h. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.

Дополнительные сведения об использовании этого флага совместно с другими функциями отладки см. в статье [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>См. также

[Флаги управления](../c-runtime-library/control-flags.md)
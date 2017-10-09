---
title: "_crtDbgFlag | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 559dba68c8c171fbc84be17e64c2628b4bbf5011
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
Флаг **_crtDbgFlag** состоит из пяти битовых полей, которые управляют отслеживанием, проверкой, созданием отчетов и созданием дампа для выделения памяти в отладочной версии кучи. Битовые поля флага задаются с помощью функции [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md). Этот флаг и его битовые поля объявляются в Crtdbg.h. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.  
  
 Дополнительные сведения об использовании этого флага совместно с другими функциями отладки см. в статье [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)

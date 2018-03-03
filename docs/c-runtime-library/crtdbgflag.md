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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b5169a9f5110e40e0d7ff7e9b036c2e28c98660
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crtdbgflag"></a>_crtDbgFlag
Флаг **_crtDbgFlag** состоит из пяти битовых полей, которые управляют отслеживанием, проверкой, созданием отчетов и созданием дампа для выделения памяти в отладочной версии кучи. Битовые поля флага задаются с помощью функции [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md). Этот флаг и его битовые поля объявляются в Crtdbg.h. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.  
  
 Дополнительные сведения об использовании этого флага совместно с другими функциями отладки см. в статье [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)
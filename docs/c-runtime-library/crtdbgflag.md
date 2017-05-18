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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f4c3a874d59095d620a04d5ebb6ac88e2bdfa66
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
Флаг **_crtDbgFlag** состоит из пяти битовых полей, которые управляют отслеживанием, проверкой, созданием отчетов и созданием дампа для выделения памяти в отладочной версии кучи. Битовые поля флага задаются с помощью функции [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md). Этот флаг и его битовые поля объявляются в Crtdbg.h. Этот флаг доступен, только если флаг [_DEBUG](../c-runtime-library/debug.md) был определен в приложении.  
  
 Дополнительные сведения об использовании этого флага совместно с другими функциями отладки см. в статье [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>См. также  
 [Флаги управления](../c-runtime-library/control-flags.md)

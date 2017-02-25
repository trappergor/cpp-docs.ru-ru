---
title: "cprintf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "cprintf"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cprintf - функция"
ms.assetid: 573e6634-d7e5-4856-8c01-627dcfbd5fc8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# cprintf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не рекомендуется использовать эту функцию POSIX.  Используйте вместо нее совместимую с ISO C\+\+ функцию [\_cprintf](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md) или ее версию с усовершенствованной безопасностью [\_cprintf\_s](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).
---
title: "/CLRHEADER | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRHEADER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRHEADER - параметр программы dumpbin"
  - "CLRHEADER - параметр (программа dumpbin)"
  - "-CLRHEADER - параметр (программа dumpbin)"
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CLRHEADER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRHEADER file  
```  
  
## Заметки  
 Здесь:  
  
 `file`  
 Файл образа, построенный с использованием параметра [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Заметки  
 Параметр CLRHEADER отображает сведения о заголовках .NET, используемых в любой управляемой программе.  При этом выводится местоположение и размер \(в байтах\) заголовка .NET и разделов в заголовке.  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
 Когда параметр \/CLRHEADER применяется для файла, скомпилированного с параметром \/clr, в выводе программы dumpbin будет присутствовать раздел **clr Header:**.  Значение аргумента **flags** указывает, какой именно параметр \/clr был использован:  
  
-   0 — \/clr \(образ может содержать машинный код\).  
  
-   1 — \/clr:safe \(образ содержит только код MSIL, может работать на любой платформе CLR и, возможно, поддается проверке\).  
  
-   3 — \/clr:pure \(образ содержит только код MSIL, но может работать только на платформах x86\).  
  
 Также существует возможность программной проверки того, был ли образ построен для среды CLR.  Для получения дополнительной информации см. [Практическое руководство. Машинный код или среда CLR: определение цели созданного изображения](../Topic/How%20to:%20Determine%20if%20an%20Image%20is%20Native%20or%20CLR.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)
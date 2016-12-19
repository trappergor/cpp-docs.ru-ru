---
title: "Предупреждение компилятора (уровень 1) C4325 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4325"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4325"
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4325
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**пропуск атрибутов для стандартной секции "**   
 ***секция* "**  
  
 Изменение атрибутов стандартного раздела не допускается.  Примеры.  
  
```  
#pragma section(".sdata", long)  
```  
  
 В этом примере стандартный раздел `.sdata`, в котором используется тип данных **short**, перезаписывается с использованием типа данных **long**.  
  
 Не допускается изменение атрибутов следующих стандартных разделов:  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Впоследствии допускается добавление дополнительных разделов.  
  
## См. также  
 [section](../../preprocessor/section.md)
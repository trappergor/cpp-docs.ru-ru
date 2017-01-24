---
title: "ML Fatal Error A1017 | Microsoft Docs"
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
  - "A1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1017"
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**отсутствует имя файла источника**  
  
 ML не удалось найти файл, чтобы получить или передать компоновщику.  
  
 Эта ошибка появляется, если предоставляемые параметры командной строки ML без указания имени файла в поступку.  Для сбора файлов, которые не имеют расширение .asm, используйте \/Ta параметр командной строки.  
  
 Эта ошибка также может быть создана путем вызова ML без параметров если переменная среды ML содержит параметры командной строки.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)
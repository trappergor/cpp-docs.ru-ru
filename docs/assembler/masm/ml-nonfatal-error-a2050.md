---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
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
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**real или не разрешается номер загрузки данных конфигурации**  
  
 Константа числа с плавающей запятой \(real\) или binary закодированных десятичного числа \(загрузить\) данных конфигураций была использована за исключением как инициализатора данных.  
  
 Одно из произойденного следующих действий:  
  
-   Вещественное число или данные конфигурации загрузки были использованы в выражении.  
  
-   Вещественное число использовался для инициализации за исключением директива [dword](../../assembler/masm/dword.md)"  [8 байт](../../assembler/masm/qword.md)или  [TBYTE](../../assembler/masm/tbyte.md).  
  
-   Загружает данные конфигурации используются для инициализации за исключением директива `TBYTE`.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)
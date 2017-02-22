---
title: "Ошибка компилятора C2415 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2415"
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2415
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый тип операнда  
  
 Код операции не использует операнды данного типа.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Код операции не поддерживает количество используемых операндов.  Следует проверить количество используемых операндов в соответствии с руководством по языку сборки.  
  
2.  Более новый процессор поддерживает инструкции с новыми типами.  Необходимо настроить параметр [\/arch \(минимальная архитектура ЦП\)](../../build/reference/arch-minimum-cpu-architecture.md) чтобы использовать более новый процессор.
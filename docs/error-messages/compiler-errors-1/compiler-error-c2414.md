---
title: "Ошибка компилятора C2414 | Microsoft Docs"
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
  - "C2414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2414"
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое число операндов  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Код операции не поддерживает количество используемых операндов.  Следует проверить количество используемых операндов в соответствии с руководством по языку сборки.  
  
2.  Новый процесс поддерживает инструкцию с различным количеством операндов.  Необходимо настроить параметр [\/arch \(минимальная архитектура ЦП\)](../../build/reference/arch-minimum-cpu-architecture.md) чтобы использовать более новый процессор.
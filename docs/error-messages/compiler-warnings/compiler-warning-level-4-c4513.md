---
title: "Предупреждение компилятора (уровень 4) C4513 | Microsoft Docs"
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
  - "C4513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4513"
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": не удалось создать деструктор  
  
 Компилятору не удалось создать деструктор по умолчанию для данного класса; деструктор не создан.  Деструктор находится в базовом классе, доступ к которому отсутствует для производного класса.  Если базовый класс содержит закрытый деструктор, его следует сделать открытым или защищенным.
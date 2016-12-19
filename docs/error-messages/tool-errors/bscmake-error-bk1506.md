---
title: "Ошибка BSCMAKE BK1506 | Microsoft Docs"
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
  - "BK1506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1506"
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка BSCMAKE BK1506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно открыть файл "имяФайла" \[: причина\]  
  
 BSCMAKE не удается открыть файл.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Файл заблокирован другим процессом.  Если в качестве параметра `reason` выводится сообщение **Отказ в разрешении**, файл может использоваться браузером.  Закройте окно обозревателя и выполните построение заново.  
  
2.  Диск переполнен.  
  
3.  Аппаратная ошибка.  
  
4.  Указанный выходной файл имеет то же имя, что и существующий подкаталог.
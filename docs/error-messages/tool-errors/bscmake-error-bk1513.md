---
title: "Ошибка BSCMAKE BK1513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка BSCMAKE BK1513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

для неинкрементного обновления требуются все файлы .SBR  
  
 BSCMAKE не может создать новый BSC\-файл, поскольку один или несколько SBR\-файлов обрезаны.  Чтобы найти имена обрезанных SBR\-файлов, прочтите предупреждения [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md), сопровождающие эту ошибку.  
  
 BSCMAKE может обновить BSC\-файл обрезанным SBR\-файлом, но не сможет собрать новый.  BSCMAKE может собрать новый BSC\-файл по следующим причинам:  
  
-   BSC\-файл отсутствует.  
  
-   Для BSC\-файла указано неверное имя файла.  
  
-   BSC\-файл поврежден.  
  
 Чтобы устранить эту проблему, нужно удалить обрезанные SBR\-файлы и перестроить решение либо очистить решение, затем перестроить его.  \(В среде разработки выберите **Сборка**, **Очистить решение**, затем **Сборка**, **Перестроить решение**.\)
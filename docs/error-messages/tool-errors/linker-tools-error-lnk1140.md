---
title: "Ошибка средств компоновщика LNK1140 | Microsoft Docs"
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
  - "LNK1140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1140"
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком много модулей для базы данных программы; выполните компоновку с \/PDB:NONE  
  
 Проект содержит больше 4096 модулей.  
  
### Возможные способы устранения данной ошибки  
  
1.  Выполните повторную компоновку с помощью [\/PDB:NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Скомпилируйте некоторые модули без отладочной информации.  
  
3.  Сократите число модулей.
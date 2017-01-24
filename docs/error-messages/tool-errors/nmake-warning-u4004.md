---
title: "Предупреждение программы NMAKE U4004 | Microsoft Docs"
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
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение программы NMAKE U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком много правил для конечного объекта "имя конечного объекта"  
  
 Для данного конечного объекта было указано более одного блока описания с использованием одиночных двоеточий \(**:**\) в качестве разделителей.  NMAKE выполняет команды первого блока описания и не обрабатывает команды последующих блоков.  
  
 Чтобы задать для нескольких зависимостях один и тот же конечный объект, следует использовать двойные двоеточия \(`::`\) в качестве разделителей в каждой строке зависимости.
---
title: "Неустранимая ошибка NMAKE U1087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1087"
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка NMAKE U1087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

зависимости с разделителями ":" и "::" не предусмотрены для одного и того же конечного объекта  
  
 Конечный объект не может быть указан в зависимостях с одинарным двоеточием \(**:**\) и двойным двоеточием \(`::`\) в качестве разделителей.  
  
 Чтобы указать конечный объект в нескольких блоках описания, следует использовать в каждой строке зависимости `::`.
---
title: "Aggregation | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++]"
  - "aggregation [C++]"
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Aggregation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В некоторых случаях реализация объекта была хотел бы воспользоваться преимуществами служб, предложенных другими, объект prebuilt.  Кроме того, он был хотел бы этот второй объект для выглядеть как естественная является частью первого.  Модель COM достигает обеих этих целей с помощью вложенность и статистическую обработку.  
  
 Агрегат означает, что содержащий \(внешний\) создает объект, содержащийся \(внутренний\) объекта как часть процесса создания и интерфейсы внутреннего объекта предоставлены внешней.  Объект позволяет быть aggregatable или нет.  Если да, то он должен соответствовать определенным правилам для агрегата работать правильно.  
  
 В основном, все вызовы метода **IUnknown**, содержащихся в объекте должны делегировать для содержащего объект.  
  
## См. также  
 [Введение в COM](../atl/introduction-to-com.md)   
 [Reusing Objects](http://msdn.microsoft.com/library/windows/desktop/ms678443)
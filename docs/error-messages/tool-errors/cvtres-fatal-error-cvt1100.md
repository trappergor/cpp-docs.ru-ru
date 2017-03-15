---
title: "Неустранимая ошибка CVTRES CVT1100 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CVT1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVT1100"
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка CVTRES CVT1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

повторяющиеся ресурсы — type:"тип", name:"имя", language:"язык", flags:"флаги", size:"размер"  
  
 Повторное определение указанного ресурса.  
  
 Эта ошибка может возникнуть при создании библиотеки типов с помощью компоновщика, если не задан параметр [\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md), а другому ресурсу проекта уже присвоен идентификатор 1.  В этом случае задайте параметр \/TLBID и укажите другое значение, не превышающее 65535.
---
title: "Ошибка компилятора C3832 | Microsoft Docs"
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
  - "C3832"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3832"
ms.assetid: 9a41df82-42e1-4908-958c-76cff9235de0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3832
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"библиотека типов": по всей видимости, библиотека типов построена для 32\-разрядных указателей; измените квалификатор "ptrsize"  
  
 Явная информация, указанная в атрибуте `ptrsize` директивы [\#import](../Topic/%23import%20Directive%20\(C++\).md), не согласуется с данными, обнаруженными компилятором в библиотеке типов.
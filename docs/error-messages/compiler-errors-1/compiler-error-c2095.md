---
title: "Ошибка компилятора C2095 | Microsoft Docs"
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
  - "C2095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2095"
ms.assetid: 44f8ada1-974f-4e81-a408-33ac6695aa53
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": фактический параметр имеет тип 'void': параметр 'number'  
  
 Параметр, переданный функции, является типом `void`, который не разрешен.  Вместо этого используйте указатель на void \(`void *`\).  
  
 `number` указывает, какой параметр является `void`.
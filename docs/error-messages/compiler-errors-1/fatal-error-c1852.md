---
title: "Неустранимая ошибка C1852 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1852"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1852"
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1852
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя\_файла" не является допустимым файлом предкомпилированного заголовка  
  
 Файл не является предкомпилированным заголовком.  
  
### Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Указан недопустимый файл с **\/Yu** или **\#pragma hdrstop**.  
  
2.  Если не указано иное, компилятор предполагает расширение файла PCH.
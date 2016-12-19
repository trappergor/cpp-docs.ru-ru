---
title: "Ошибка компилятора C3163 | Microsoft Docs"
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
  - "C3163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3163"
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"construct": атрибуты не согласованы с предыдущим объявлением  
  
 Атрибуты, применяемые к определению, конфликтуют с атрибутами, применяемыми к объявлению.  
  
 Один из способов устранения ошибки C3163 заключается в удалении атрибутов из опережающего объявления.  Все атрибуты в опережающем объявлении должны быть меньше атрибутов определения или, по крайней мере, равны им.  
  
 Возможная причина ошибки C3163 связана с языком заметок к исходному коду Майкрософт \(SAL\).  Макрос SAL развертывается только после компиляции проекта с флагом **\/analyze**.  Программа, скомпилированная без флага \/analyze, может создавать ошибку C3163 при попытке ее повторной компиляции с параметром \/analyze.  Дополнительные сведения о SAL см. в разделе [Примечания SAL](../../c-runtime-library/sal-annotations.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3163.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## См. также  
 [Примечания SAL](../../c-runtime-library/sal-annotations.md)
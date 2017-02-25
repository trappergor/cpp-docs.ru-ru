---
title: "Предупреждение компилятора (уровень 4) C4431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4431"
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 4) C4431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

отсутствует спецификатор типа — предполагается int.Примечание. C\+\+ не поддерживает тип int по умолчанию  
  
 Это ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005: Visual C\+\+ по умолчанию больше не создает нетипизированные идентификаторы \(такие как int\).  Тип идентификатора должен быть задан явным образом.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C4431.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```
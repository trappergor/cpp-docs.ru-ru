---
title: "Трансляция. Диагностика | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Трансляция. Диагностика
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.1.3** Определение диагностики  
  
 Microsoft C создает сообщения об ошибках в следующем виде:  
  
```  
  
filename( line-number ) : diagnostic Cnumber message  
```  
  
 где *имя\-файла* — имя исходного файла, в котором была обнаружена ошибка; *номер\-строки* — номер строки, в которой компилятор обнаружил ошибку; `diagnostic` — "ошибка" или "предупреждение"; `number` — уникальное 4\-значное число \(с предшествующим символом **C**, как указано в синтаксисе\), определяющее ошибку или предупреждение; `message` — поясняющее сообщение.  
  
## См. также  
 [Поведение, определяемое реализацией](../c-language/implementation-defined-behavior.md)
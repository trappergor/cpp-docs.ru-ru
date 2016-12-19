---
title: "Хранение строковых литералов | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "строковые литералы, хранение"
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Хранение строковых литералов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Символы строкового литерала хранятся по порядку в смежных адресах памяти.  Escape\-последовательность \(например, **\\\\** или **\\"**\) внутри строкового литерала считается отдельным символом.  Нуль\-символ \(представленный escape\-последовательностью **\\0** \), автоматически добавляется в каждый строковый литерал и отмечает его конец. \(Это происходит на [этапе преобразования](../preprocessor/phases-of-translation.md) 7.\) Обратите внимание, что компилятор может не сохранить две одинаковые строки с двумя разными адресами.  [\/GF](../Topic/-GF%20\(Eliminate%20Duplicate%20Strings\).md) указывает компилятору поместить только одну копию одинаковых строк в исполняемый файл.  
  
## Примечания  
 **Блок, относящийся только к системам Microsoft**  
  
 Строки имеют статическую длительность хранения.  Дополнительные сведения о длительности хранения см. в разделе [Классы хранения](../c-language/c-storage-classes.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Строковые литералы в C](../c-language/c-string-literals.md)
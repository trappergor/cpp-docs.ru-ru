---
title: "Предупреждение компилятора ресурсов RW4004 | Microsoft Docs"
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
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора ресурсов RW4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Символ ASCII не соответствует виртуальному коду клавиши  
  
 Строковый литерал был использован для виртуального кода клавиши в сочетании клавиш типа VIRTKEY.  
  
 Данное предупреждение позволяет продолжить операцию. Однако оно сообщает, что созданные сочетания клавиш могут не соответствовать указанной строке \(сочетания клавиш VIRTKEY используют коды клавиш, отличные от кодов для сочетаний клавиш ASCII\).  
  
 Если строковые литералы являются синтаксически правильными, можно проверить соответствие сочетаний клавиш с помощью значения **VK\_\* \#define** в WINDOWS.h.
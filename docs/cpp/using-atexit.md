---
title: "Использование atexit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit - функция"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование atexit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью функции [atexit](../c-runtime-library/reference/atexit.md) можно указать функцию обработки выхода, которая выполняется перед завершением работы программы.  Никакие глобальные статические объекты, инициализированные до вызова функции `atexit`, не уничтожаются до вызова функции обработки выхода.  
  
## См. также  
 [Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)
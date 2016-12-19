---
title: "Включаемые файлы для многопоточности | Microsoft Docs"
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
helpviewer_keywords: 
  - "включить файлы, многопоточность"
  - "многопоточность [C++], включить файлы"
  - "работа с потоками [C++], включить файлы"
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Включаемые файлы для многопоточности
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Стандартные включаемые файлы объявляют функции библиотеки среды выполнения языка C, как они реализованы в библиотеках.  Если используется параметр [Полная оптимизация](../../build/reference/ox-full-optimization.md) \(\/Ox\) или [Соглашение о вызовах fastcall](../../build/reference/gd-gr-gv-gz-calling-convention.md) \(\/Gr\), компилятор считает, что все функции должны вызываться с использованием соглашения о вызовах реестра.  Функции библиотеки среды выполнения скомпилированы с помощью соглашения о вызовах языка С, и объявления в стандартных включаемых файлах указывают компилятору на необходимость создания правильных внешних ссылок на эти функции.  
  
## См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../../parallel/multithreading-with-c-and-win32.md)
---
title: "Внутренний и подставляемый ассемблерный код | Microsoft Docs"
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
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Внутренний и подставляемый ассемблерный код
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Одним из ограничений компилятора [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] является отсутствие поддержки подставляемого ассемблерного кода.  Это значит, что функции, которые нельзя написать средствами языков C или C\+\+, должны быть представлены в виде подпрограмм или внутренних функций, поддерживаемых компилятором.  Некоторые функции чувствительны к производительности, другие – нет.  Функции, чувствительные к производительности, должны быть реализованы как внутренние функции.  
  
 Описание встроенных средств, поддерживаемых компилятором, представлено в документе [Встроенные средства компилятора](../intrinsics/compiler-intrinsics.md).  
  
## См. также  
 [Программные соглашения x64](../build/x64-software-conventions.md)
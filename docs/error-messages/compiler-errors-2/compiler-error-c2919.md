---
title: "Compiler Error C2919 | Microsoft Docs"
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
  - "C2919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2919"
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type: операторы не могут напрямую использоваться на опубликованной поверхности типа WinRT.  
  
 Система с типом среды выполнения Windows не поддерживает функции — члены оператора на опубликованной поверхности типа.  Это вызвано тем, что не все языки могут использовать функции — члены оператора.  Вы можете создать закрытые или внутренние функции — члены оператора, которые можно вызывать из кода C\+\+ в том же классе или блоке компиляции.  
  
 Чтобы устранить эту проблему, удалите функцию — член оператора из открытого интерфейса или измените ее на именованную функцию\-член.  Например, вместо `operator==` назовите функцию\-член `Equals`.
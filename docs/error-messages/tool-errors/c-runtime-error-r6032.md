---
title: "Ошибка во время выполнения C R6032 | Microsoft Docs"
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
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка во время выполнения C R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Недостаточно места для сведений о языковых стандартах  
  
 Среда выполнения помещает сведения о языковых стандартах в каждый из потоков, чтобы обрабатывать вызовы функций, зависящих от языковых стандартов.  Если не удается выделить память для данных сведений, среда выполнения не сможет продолжать работу, поскольку эти данные влияют на слишком большое число основных функциональных возможностей среды выполнения.
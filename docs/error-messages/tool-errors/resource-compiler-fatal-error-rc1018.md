---
title: "Неустранимая ошибка компилятора ресурсов RC1018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1018"
ms.assetid: bb1d2efd-6898-412f-bb03-9ff94c54e4dc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка компилятора ресурсов RC1018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

непредвиденная директива "\#elif"  
  
 Директива `#elif` не отображается в конструкции `#if`, **\#ifdef** или **\#ifndef**.  
  
 Убедитесь, что перед этим оператором действительно имеется оператор `#if`, **\#ifdef** или **\#ifndef**.
---
title: "Неустранимая ошибка C1207 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1207"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1207"
ms.assetid: cd31b410-9523-47db-883c-e69a9351ffa2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1207
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляемые шаблоны не поддерживаются установленной версией среды выполнения  
  
 Ошибка C1207 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1207, следует установить версию среды CLR, предназначенную для использования с компилятором.
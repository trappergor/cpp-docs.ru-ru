---
title: "Ошибка средств компоновщика LNK2008 | Microsoft Docs"
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
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Целевой объект адресной привязки не выравнивается по 'symbol\_name'  
  
 LINK обнаружил адресную привязку объекта в объектном файле, которая не была правильно выровнена.  
  
 Эта ошибка может быть вызвана выравниванием пользовательского раздела \(например \#pragma [pack](../../preprocessor/pack.md)\), модификатором [align](../../cpp/align-cpp.md), или использованием ассемблерного кода, который изменяет выравнивание раздела.  
  
 Если в вашем коде не используется ничего из вышеперечисленного, эта ошибка может быть вызвана компилятором.
---
title: "Предупреждение компилятора (уровень 1) C4027 | Microsoft Docs"
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
  - "C4027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4027"
ms.assetid: f30d57b9-20c4-4284-8686-566d9f0ca7fc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция объявлена без списка формальных параметров  
  
 В объявлении функции отсутствуют формальные параметры, но существуют формальные параметры в определении функции или фактические параметры в вызове. При последующих вызовах этой функции предполагается, что функция принимает фактические параметры типов, найденных в определении функции или в вызове.
---
title: "Предупреждение компилятора (уровень 4) C4234 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4234"
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: ключевое слово "ключевое слово" зарезервировано для использования в будущем  
  
 В настоящий момент компилятор не реализует используемое ключевое слово.  
  
 Данное предупреждение автоматически переходит в разряд ошибки.  Для устранения этого состояния следует использовать предупреждение директивы [\#pragma](../../preprocessor/warning.md).  Например, чтобы преобразовать предупреждение C4234 в предупреждение уровня 4, необходимо использовать  
  
```  
#pragma warning(2:4234)  
```  
  
 в файле исходного кода.
---
title: "Предупреждение компилятора (уровень 4) C4235 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4235"
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 4) C4235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение: ключевое слово "ключевое слово" данной архитектурой не поддерживается  
  
 Компилятор не поддерживает используемое ключевое слово.  
  
 Данное предупреждение автоматически переходит в разряд ошибки.  Для устранения этого состояния следует использовать предупреждение директивы [\#pragma](../../preprocessor/warning.md).  Например, чтобы перевести предупреждение компилятора C4235 на уровень 2, используйте следующую строку кода  
  
```  
#pragma warning(2:4235)  
```  
  
 в файле исходного кода.
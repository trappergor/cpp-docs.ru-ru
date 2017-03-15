---
title: "Ошибка компилятора C2857 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2857"
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

оператор "\#include", указанный с параметром командной строки \/Ycимя\_файла, не найден в исходном файле  
  
 Параметр [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) указывает имя включенного файла, который не включается в исходный файл при компиляции.  
  
 Эта ошибка может быть вызвана оператором `#include` в нескомпилированном блоке условной компиляции.
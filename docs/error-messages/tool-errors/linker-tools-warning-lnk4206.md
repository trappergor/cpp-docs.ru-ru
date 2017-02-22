---
title: "Предупреждение средств компоновщика LNK4206 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4206"
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение средств компоновщика LNK4206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не найдены сведения о предкомпилированном типе; "имя файла" не скомпоновано или перезаписано; компоновка объекта выполняется как при отсутствии отладочных данных  
  
 Данный объектный файл, компилированный с параметром [\/Yc](../../build/reference/yc-create-precompiled-header-file.md), либо не был задан в команде LINK, либо был перезаписан.  
  
 Как правило, данное предупреждение вызывается случае, когда OBJ\-файл, который компилировался с параметром \/Y, находится в библиотеке, и при этом отсутствуют символические ссылки из кода на данный OBJ\-файл.  В таком случае компоновщик не будет использовать \(и не обнаружит\) OBJ\-файл.  В данной ситуации следует повторно выполнить компиляцию кода и использовать параметр [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) для остальных объектов \(объектов, которые не компилировались с параметром \/Yc\).
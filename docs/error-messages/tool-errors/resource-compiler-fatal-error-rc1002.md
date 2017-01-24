---
title: "Неустранимая ошибка компилятора ресурсов RC1002 | Microsoft Docs"
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
  - "RC1002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1002"
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка компилятора ресурсов RC1002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не хватает памяти в куче.  
  
### Возможные способы устранения данной ошибки  
  
1.  Увеличьте размер файла подкачки Windows.  Дополнительные сведения об увеличении размера файла подкачки см. в разделе "виртуальная память" в справке Windows.  
  
2.  Разделите текущий файл на меньшие по размеру и скомпилируйте их отдельно.  
  
3.  Удалите другие программы или драйверы, запущенные системой.
---
title: "Неустранимая ошибка компилятора ресурсов RW1025 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW1025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW1025"
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка компилятора ресурсов RW1025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Недостаточно памяти в дальней куче  
  
 Необходимо проверить наличие резидентных программ, которые могут занимать слишком много ресурсов.  Можно использовать программу CHKDSK, чтобы выяснить доступные ресурсы памяти.  
  
 При создании большого файла ресурса следует разбить скрипт ресурса на два файла.  После создания двух RES\-файлов следует использовать командную строку MS\-DOS, чтобы выполнить их слияние:  
  
```  
copy first.res /b + second.res /b full.res  
```
---
title: "Неустранимая ошибка NMAKE U1095 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1095"
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка NMAKE U1095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком длинная после подстановки командная строка "командная\_строка"  
  
 После расширения макроса длина данной командной строки превышает ограничение, установленное для данной операционной системы.  
  
 Допустимая длина командной строки в MS\-DOS — 128 символов.  
  
 Если команда предназначена для программы, принимающей команды командной строки из файла, следует изменить команду и обеспечить ввод из файла на диске или подставляемого файла.  Например, программы LINK и LIB принимают ввод команд из файла отклика.
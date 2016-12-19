---
title: "Ошибка средств компоновщика LNK1201 | Microsoft Docs"
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
  - "LNK1201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1201"
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ошибка при записи в базу данных "имя файла" программы; возможно, не хватает места на диске, недопустимый путь или недостаточно прав  
  
 LINK не удается выполнить запись файла вывода в базу данных программы \(БДП\).  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Файл поврежден.  Удалите файл и выполните компоновку еще раз.  
  
2.  Недостаточно места на диске для записи файла.  
  
3.  Диск недоступен, возможно, вследствие неполадок в сети.  
  
4.  Запущен отладчик для программы, компоновка которой выполняется в данный момент.  
  
5.  Не хватает памяти в куче.  Дополнительные сведения см. в разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md).
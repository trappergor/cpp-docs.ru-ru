---
title: "Формат образа | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Формат образа
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В качестве формата исполняемого образа используется PE32\+.  Максимальный размер файла исполняемого образа \(как для DLL\-файлов, так и для EXE\-файлов\) не может превышать 2 ГБ. Это позволяет применять относительную адресацию с использованием 32\-разрядного смещения для обращения к статическим данным образа.  К таким данным относятся таблицы адресов импорта, строковые константы, статические глобальные данные и т. д.  
  
## См. также  
 [Программные соглашения x64](../build/x64-software-conventions.md)
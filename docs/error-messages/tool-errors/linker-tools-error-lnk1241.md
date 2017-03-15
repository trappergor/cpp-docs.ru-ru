---
title: "Ошибка средств компоновщика LNK1241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка средств компоновщика LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

файл ресурсов "файл ресурсов" уже указан  
  
 Эта ошибка возникает в том случае, если OBJ\-файл, полученный при запуске средства **cvtres** вручную из командной строки, передается компоновщику вместе с другими RES\-файлами.  
  
 Чтобы задать несколько RES\-файлов, следует передавать их компоновщику в виде RES\-файлов, а не созданных с помощью средства **cvtres** OBJ\-файлов.
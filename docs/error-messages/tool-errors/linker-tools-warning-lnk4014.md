---
title: "Предупреждение средств компоновщика LNK4014 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4014"
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение средств компоновщика LNK4014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается найти объект\-член "имяобъекта"  
  
 Программе LIB не удалось найти `objectname` в библиотеке.  
  
 Параметры **\/REMOVE** и **\/EXTRACT** требуют полное имя объекта\-члена, удаляемого или копируемого в файл.  В полное имя входит путь исходного объектного файла.  Для просмотра полных имен объектов\-членов библиотеки используется команда DUMPBIN [\/ARCHIVEMEMBERS](../Topic/-ARCHIVEMEMBERS.md) или LIB [\/LIST](../../build/reference/managing-a-library.md).
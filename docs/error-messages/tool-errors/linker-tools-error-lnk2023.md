---
title: "Ошибка средств компоновщика LNK2023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2023"
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка средств компоновщика LNK2023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

библиотека DLL или точка входа \<dll or entry point\>  
  
 Компоновщик загружает неверную версию библиотеки msobj90.dll.  Убедитесь в том, что версия программы link.exe совпадает с версией библиотеки msobj90.dll, присутствующей в пути.  
  
 Может отсутствовать библиотека, от которой зависит библиотека msobj90.dll.  Список библиотек, от которых зависит msobj90.dll:  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Проверьте, нет ли на компьютере устаревших копий библиотеки msobj90.dll.
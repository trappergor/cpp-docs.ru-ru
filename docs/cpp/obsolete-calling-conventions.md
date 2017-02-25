---
title: "Устаревшие соглашения о вызовах | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fortran"
  - "__pascal"
  - "__syscall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fortran - ключевое слово [C++]"
  - "__pascal - ключевое слово [C++]"
  - "__syscall - ключевое слово [C++]"
  - "соглашения при вызове, устарело"
  - "WINAPI"
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Устаревшие соглашения о вызовах
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 Соглашения о вызовах **\_\_pascal**, **\_\_fortran** и **\_\_syscall** больше не поддерживаются.  Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.  
  
 WINDOWS.H теперь поддерживает макрос **WINAPI**, который преобразуется в соответствующее соглашение о вызовах для целевого объекта.  Используйте **WINAPI** в случаях, когда ранее использовался **PASCAL** или **\_\_far \_\_pascal**.  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [Передача аргументов и соглашения именования](../Topic/Argument%20Passing%20and%20Naming%20Conventions.md)
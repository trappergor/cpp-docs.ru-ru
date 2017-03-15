---
title: "Предупреждение при построении проекта PRJ0041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0041"
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение при построении проекта PRJ0041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не удается найти отсутствующую зависимость "зависимость" для файла "файл".Проект все же можно построить, но пока этот файл не найден, возможно, проект будет считаться устаревшим.  
  
 Файл \(файл ресурсов или .idl\/.odl\-файл\), например, содержал оператор "include", который не был разрешен системой.  
  
 Поскольку система проекта не обрабатывает операторы процессора \(например, \#if\), несоответствующий оператор может не быть частью построения.  
  
 Для устранения предупреждения удалите весь лишний код из RC\-файла или вставьте местозаполняющие файлы с соответствующим именем.
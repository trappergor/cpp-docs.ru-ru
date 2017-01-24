---
title: "Ошибка построения проекта PRJ0028 | Microsoft Docs"
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
  - "PRJ0028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0028"
ms.assetid: 0a6e0da7-cb3d-40b6-81a6-6196a9c2526b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Временный файл "файл" содержит содержимое в кодировке Юникод, которое невозможно преобразовать к кодовой странице ANSI пользователя.  
  
 С параметром компоновщика [\/MIDL \(указание параметров командной строки MIDL\)](../../build/reference/midl-specify-midl-command-line-options.md) указано значение, которое не удалось разрешить с помощью кодовой страницы системы.  
  
 Кодовая страница, используемая при указании команды MIDL \(кодовая страница ввода\), должна совпадать с кодовой страницей системы.
---
title: "Неустранимая ошибка NMAKE U1059 | Microsoft Docs"
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
  - "U1059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1059"
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка: отсутствие "}" в зависимости  
  
 Путь поиска для зависимости был указан некорректно.  Были утрачены пробелы или фигурные скобки в строке пути \(**}**\).  
  
 Синтаксисом спецификации директории для зависимости является  
  
 **{**   
 ***каталоги* }зависимые**  
  
 где `directories` определяет один или более путей, которые отделяются друг от друга при помощи точки с запятой \(**;**\).  Пробелы не разрешаются.  
  
 При замене части всех путей поиска макросом убедитесь, что в расширении макроса нет пробелов.
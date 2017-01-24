---
title: "Ошибка компилятора ресурсов RC2124 | Microsoft Docs"
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
  - "RC2124"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2124"
ms.assetid: 4eb5c4ec-ca9b-46a0-805b-35e040e9ed41
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора ресурсов RC2124
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не ожидалось пустое меню  
  
 Ключевое слово **END** возникает перед любым элементом меню, определенном в операторе **MENU**.  Компилятор ресурсов не допускает использование пустого меню.  Убедитесь, что Вы не открывали кавычки в операторе **MENU**.
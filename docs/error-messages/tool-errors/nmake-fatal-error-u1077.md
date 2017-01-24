---
title: "Неустранимая ошибка NMAKE U1077 | Microsoft Docs"
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
  - "U1077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1077"
ms.assetid: 70d989f8-ef34-4ad7-8fe0-5b800556b2a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"программа": возвращенный код "значение"  
  
 Сбой указанной команды или программы, вызываемой программой NMAKE \(возвращается указанный код выхода\).  
  
 Чтобы отключить эту ошибку и продолжить сеанс программы NMAKE, используйте параметр \/I, директиву **.IGNORE** или модификатор команд "тире" \(**\-**\).  Чтобы продолжить сеанс программы NMAKE для несвязанных компонентов дерева зависимостей, используйте параметр \/K.
---
title: "Ошибка во время выполнения C R6028 | Microsoft Docs"
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
  - "R6028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6028"
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 9
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка во время выполнения C R6028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается инициализировать кучу  
  
 Эта ошибка возникает в том случае, если в операционной системе не удается создать пул памяти для приложения.  Например, в библиотеке времени выполнения C \(CRT\) вызывается функция `HeapCreate` Win32, в результате чего возвращается свидетельствующее об ошибке значение NULL.  
  
 Если эта ошибка возникает во время запуска приложения, система может не удовлетворять запросы кучи из\-за того, что загруженные драйверы содержат ошибки.  Проверьте наличие обновленных драйверов в Центре обновления Windows или на веб\-сайте производителя оборудования.
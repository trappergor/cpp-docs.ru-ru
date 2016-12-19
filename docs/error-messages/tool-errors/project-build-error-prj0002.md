---
title: "Ошибка построения проекта PRJ0002 | Microsoft Docs"
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
  - "PRJ0002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0002"
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

результат ошибки возвращен из "command line".  
  
 Команда ***command line***, которая была создана из пользовательского ввода в диалоговом окне **Страницы свойств**, возвратила код ошибки, но сведения не отобразились в окне вывода.  
  
 Разрешение для этой ошибки зависит от того, какой инструмент создает ошибку.  Для MIDL можно получить сведения о неполадках, если определено \/o \(перенаправление вывода\).  
  
 Вызов пакетного файла, например, настраиваемого этапа построения или построения события, не показывающего сведения о сбоях, также может послужить причиной возникновения этой ошибки.
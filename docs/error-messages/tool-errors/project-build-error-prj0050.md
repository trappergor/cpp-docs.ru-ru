---
title: "Ошибка построения проекта PRJ0050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0050"
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка построения проекта PRJ0050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не удалось зарегистрировать выходной файл.Убедитесь, что у вас есть достаточные разрешения на изменение реестра.  
  
 Системе построения Visual C\+\+ не удалось зарегистрировать выходной файл построения \(DLL или EXE\).  Для изменения реестра необходим вход в систему с учетной записью администратора.  
  
 При построении библиотеки DLL можно попробовать зарегистрировать ее динамически с помощью программы regsvr32.exe — при этом будет выведена информация о причинах сбоя регистрации.  
  
 Если строится не DLL, следует найти в журнале построения команду, выполнение которой привело к ошибке.
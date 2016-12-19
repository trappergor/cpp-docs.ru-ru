---
title: "Неустранимая ошибка C1033 | Microsoft Docs"
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
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается открыть базу данных программы "pdb"  
  
 Данная ошибка может быть вызвана дисковой ошибкой.  
  
 Языковой стандарт пользователя в Visual C\+\+ .NET 2002 должен быть правильно установлен, если имя файла \(или путь каталога файла\) содержит символы многобайтовой кодировки.  Установка языкового стандарта системы недостаточна; языковой стандарт пользователя должен быть настроен на обработку символов многобайтовой кодировки.  
  
 Дополнительные сведения в разделе см. в [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).
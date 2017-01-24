---
title: "Ошибка построения проекта PRJ0024 | Microsoft Docs"
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
  - "PRJ0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0024"
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не удается преобразовать Юникод\-путь "путь" в ANSI кодовую страницу пользователя.  
  
 ***путь***  — исходная версия строки пути в формате Юникод.  Эта ошибка возникает в том случае, если невозможно преобразовать путь в формате Юникод непосредственно в формат ANSI для используемой в системе кодовой страницы.  
  
 Эта ошибка может возникнуть при работе с проектами, созданными в системах, в которых используется кодовая страница, недоступная на компьютере разработчика.  
  
 Чтобы устранить ошибку, используйте в пути текст в формате ANSI или установите на компьютер соответствующую кодовую страницу и зарегистрируйте ее в системе в качестве используемой по умолчанию.
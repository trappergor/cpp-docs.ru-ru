---
title: "Ошибка построения проекта PRJ0008 | Microsoft Docs"
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
  - "PRJ0008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0008"
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не удалось удалить файл "файл".  
  
 **Необходимо убедиться, что файл не используется другим процессом и не защищен от записи.**  
  
 Во время построения или очистки Visual C\+\+ удаляет все известные промежуточные файлы и файлы вывода для сборки, а также любые файлы, которые соответствуют характеристикам подстановочного знака в свойстве **Расширения, подлежащие удалению во время очистки** на странице свойств [Общие настройки конфигурации](../Topic/General%20Property%20Page%20\(Project\).md).  
  
 Данная ошибка возникает в том случае, если Visual C\+\+ не удается удалить файл.  Чтобы разрешить данную ошибку, следует предоставить пользователю, выполняющему построение, возможность записи в файл и каталог, в котором он содержится.
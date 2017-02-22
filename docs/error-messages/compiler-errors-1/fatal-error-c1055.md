---
title: "Неустранимая ошибка C1055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: закончились ключи  
  
 Файл исходного кода содержит слишком много символов.  Компилятору недостаточно хэш\-ключей для таблицы символов.  
  
### Возможные способы устранения данной ошибки  
  
1.  Разбейте файл исходного кода на несколько файлов меньшего размера.  
  
2.  Удалите ненужные заголовочные файлы.  
  
3.  Повторно используйте временные и глобальные переменные вместо создания новых.
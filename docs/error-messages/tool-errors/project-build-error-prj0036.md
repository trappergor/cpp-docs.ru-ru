---
title: "Ошибка построения проекта PRJ0036 | Microsoft Docs"
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
  - "PRJ0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0036"
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка построения проекта PRJ0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Свойство 'Дополнительные файлы' для средства веб\-развертывания содержит недопустимую запись.  
  
 В свойстве "Дополнительные файлы" на странице "Веб\-развертывание" содержится ошибка, возможно, из\-за проблемы выполнения макроса.  Эта ошибка также может означать, что путь неправильно сформирован — содержит знаки или сочетания знаков, недопустимые в пути файла.  
  
 Чтобы устранить эту ошибку, исправьте макрос или спецификацию пути.  Анализируемый путь является абсолютным путем относительно каталога проекта.  
  
 Эта ошибка также может означать, что один из файлов, на который есть ссылка, не существует.
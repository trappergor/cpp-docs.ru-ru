---
title: "Математическая ошибка M6108 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6108"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6108"
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Математическая ошибка M6108
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

квадратный корень  
  
 Отрицательный операнд в операции извлечения квадратного корня.  
  
 Программа завершается с кодом выхода 136.  
  
> [!NOTE]
>  Функция `sqrt` в библиотеке времени выполнения C и встроенная функция FORTRAN **SQRT** не создают эту ошибку.  Функция C `sqrt` проверяет аргумент перед выполнением операции и возвращает значение ошибки, если операнд оказывается отрицательным.  Функция FORTRAN **SQRT** вместо этой ошибки создает ошибку DOMAIN [M6201](../../error-messages/tool-errors/math-error-m6201.md).
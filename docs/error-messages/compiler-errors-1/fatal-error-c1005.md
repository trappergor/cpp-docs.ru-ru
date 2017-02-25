---
title: "Неустранимая ошибка C1005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1005"
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Неустранимая ошибка C1005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком большая строка для буфера  
  
 Строка в промежуточном файле компилятора вызвала переполнение буфера.  
  
 Эта ошибка может возникнуть, если размер параметра, передаваемого в параметр компилятора [\/Fd](../../build/reference/fd-program-database-file-name.md) или [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md), превышает 256 байт.
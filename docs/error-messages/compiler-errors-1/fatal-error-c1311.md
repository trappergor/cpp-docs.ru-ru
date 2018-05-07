---
title: Неустранимая ошибка C1311 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53b3759a5fec4b072f9a9b300670d61cb0d101c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1311"></a>Неустранимая ошибка C1311
Формат COFF не может выполнить статическую инициализацию «var» с байтах адреса  
  
 Адрес, значение которого не известна во время компиляции не может назначаться статически переменной, тип которой имеет хранилище размером менее четырех байт.  
  
 Эта ошибка может возникать в коде, в противном случае — допустимое C++.  
  
 В следующем примере показано одно условие, которое может вызывать ошибку C1311.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```
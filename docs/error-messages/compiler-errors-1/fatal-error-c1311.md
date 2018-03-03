---
title: "Неустранимая ошибка C1311 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0d798ea53ebbbfe850b77b4b8176b35e2040ed8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
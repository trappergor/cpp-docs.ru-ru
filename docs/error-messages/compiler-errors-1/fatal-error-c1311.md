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
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9aeb63e041ddfe26a8fc47afc838f2f5c3ce35d6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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

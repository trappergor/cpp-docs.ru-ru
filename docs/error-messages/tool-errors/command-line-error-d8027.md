---
title: "Ошибка командной строки D8027 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8027
dev_langs: C++
helpviewer_keywords: D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e52c3c3029a8828aef11637a21f862cbe33cf9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-error-d8027"></a>Ошибка командной строки D8027
не удается выполнить «компонент»  
  
 Компилятору не удалось запустить указанный компонент компилятора или компоновщика.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Недостаточно памяти для загрузки компонента. Если NMAKE вызван компилятор, запустите компилятор вне файла makefile.  
  
2.  Текущая операционная система не может запустить компонент. Убедитесь, что точки пути к исполняемым файлам подходящим для операционной системы.  
  
3.  Компонент поврежден. Повторно скопируйте компонент с установочных дисков, с помощью программы установки.  
  
4.  Параметр был указан неправильно. Например:  
  
    ```  
    cl /B1 file1.c  
    ```
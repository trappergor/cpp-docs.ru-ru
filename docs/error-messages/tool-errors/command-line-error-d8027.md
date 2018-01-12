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
ms.workload: cplusplus
ms.openlocfilehash: 1bd66688dbf582bf38fb9a0a3706663db3cf145d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8027"></a>Ошибка командной строки D8027
не удается выполнить «компонент»  
  
 Компилятору не удалось запустить указанный компонент компилятора или компоновщика.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Недостаточно памяти для загрузки компонента. Если NMAKE вызван компилятор, запустите компилятор вне файла makefile.  
  
2.  Текущая операционная система не может запустить компонент. Убедитесь, что точки пути к исполняемым файлам подходящим для операционной системы.  
  
3.  Компонент поврежден. Повторно скопируйте компонент с установочных дисков, с помощью программы установки.  
  
4.  Параметр был указан неправильно. Пример:  
  
    ```  
    cl /B1 file1.c  
    ```
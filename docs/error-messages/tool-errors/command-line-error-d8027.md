---
title: Ошибка командной строки D8027 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc93edb939001a1e1bed5d3f7a4113e8483e81dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296124"
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
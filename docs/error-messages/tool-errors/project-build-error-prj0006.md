---
title: "Ошибка построения проекта PRJ0006 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0006
dev_langs: C++
helpviewer_keywords: PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 817450fb6b72f985d7ff49f7e65f9dfa0933b4d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0006"></a>Ошибка построения проекта PRJ0006
Не удалось открыть временный файл «файл». Убедитесь, что файл существует и что каталог не защищен от записи.  
  
 Visual C++ не удалось создать временный файл во время построения. Возможные причины:  
  
-   Отсутствует временный каталог.  
  
-   Временный каталог только для чтения.  
  
-   Недостаточно места на диске.  
  
-   $(Intdir) защищен только для чтения или содержит временные файлы, которые доступны только для чтения.  
  
 Эта ошибка также возникает следующая ошибка PRJ0007: не удалось создать выходной каталог «каталог». Ошибка PRJ0007 означает, что не удалось создать каталог $(IntDir) подразумевает создание временно файлов также не будет работать.  
  
 Временные файлы создаются при указании:  
  
-   Файл ответа.  
  
-   Этап настраиваемого построения.  
  
-   События построения.
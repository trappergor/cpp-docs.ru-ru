---
title: "Неустранимая ошибка NMAKE U1056 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41db646e2559051c11de5265900dde8ad0a03214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056
не удается найти процессор команд  
  
 Обработчик команд не находился в пути, указанном в **COMSPEC** или **путь** переменные среды.  
  
 Программа NMAKE использует COMMAND.COM или CMD. EXE от имени командного процессора при выполнении команд. Выполняет поиск обработчика команд сначала в пути, заданном в **COMSPEC**. Если **COMSPEC** не существует, NMAKE поиск в каталогах, указанных в **путь**.
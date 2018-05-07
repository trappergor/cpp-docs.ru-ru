---
title: Неустранимая ошибка NMAKE U1056 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19890e290c98fd9602d755ad35f9d47204bd6c24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056
не удается найти процессор команд  
  
 Обработчик команд не находился в пути, указанном в **COMSPEC** или **путь** переменные среды.  
  
 Программа NMAKE использует COMMAND.COM или CMD. EXE от имени командного процессора при выполнении команд. Выполняет поиск обработчика команд сначала в пути, заданном в **COMSPEC**. Если **COMSPEC** не существует, NMAKE поиск в каталогах, указанных в **путь**.
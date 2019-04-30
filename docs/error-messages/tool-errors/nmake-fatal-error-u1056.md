---
title: Неустранимая ошибка NMAKE U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: b15b14c04dd91ae648ea4311612c122f04f90477
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367269"
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056

не удается найти процессор команд

Интерпретатор командной строки не находился в каталоге, указанном в **COMSPEC** или **путь** переменные среды.

Программа NMAKE использует COMMAND.COM или CMD. EXE-файла в качестве обработчика команды при выполнении команд. Он сначала ищет для обработки команды в пути, заданном в **COMSPEC**. Если **COMSPEC** не существует, поиск NMAKE, каталоги, заданные в **путь**.
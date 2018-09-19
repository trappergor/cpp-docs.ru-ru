---
title: Неустранимая ошибка NMAKE U1056 | Документация Майкрософт
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
ms.openlocfilehash: e0a83c62bedf995708d5e99fee19f05696d05c2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065703"
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056

не удается найти процессор команд

Интерпретатор командной строки не находился в каталоге, указанном в **COMSPEC** или **путь** переменные среды.

Программа NMAKE использует COMMAND.COM или CMD. EXE-файла в качестве обработчика команды при выполнении команд. Он сначала ищет для обработки команды в пути, заданном в **COMSPEC**. Если **COMSPEC** не существует, поиск NMAKE, каталоги, заданные в **путь**.
---
title: Неустранимая ошибка NMAKE U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: 10131e518fa608292fff58672ede36390bcd665b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182907"
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056

не удается найти обработчик команд

Обработчик команд не находится в пути, указанном в переменных среды **ComSpec** или **path** .

NMAKE использует COMMAND.COM или CMD. EXE в качестве обработчика команд при выполнении команд. Он сначала ищет обработчик команд в пути, установленном в **ComSpec**. Если **ComSpec** не существует, NMAKE выполняет поиск в каталогах, указанных в параметре **path**.

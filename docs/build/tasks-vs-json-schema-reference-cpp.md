---
title: Справочник по схеме Tasks.VS.JSON (C++)
ms.date: 02/11/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: d0f62f6cddf3701da391880532bd2f554cc19130
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826446"
---
# <a name="tasksvsjson-c"></a>Tasks.vs.json (C++)

Файл `tasks.vs.json` можно добавить в проект "Открыть папку", чтобы определить в этом файле любую произвольную задачу, а затем вызывать ее из контекстного меню **обозревателя решений**. Проекты CMake обычно не используют этот файл, так как все команды сборки указываются в `CMakeLists.txt`. Для систем сборки, отличных от CMake, здесь можно задавать команды сборки и вызывать скрипты сборки. Общие сведения об использовании tasks.vs.json см. в разделе [Настройка задач сборки и отладки для режима разработки "Открытая папка"](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).


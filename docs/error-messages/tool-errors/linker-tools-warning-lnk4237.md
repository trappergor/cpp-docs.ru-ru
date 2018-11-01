---
title: Предупреждение средств компоновщика LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 62ce0a0edc7f15bc5a19e4630133976f413da35a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588621"
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237

/SUBSYSTEM:NATIVE, указанный при импорте из «dll»; Используйте/SUBSYSTEM: Console или/SUBSYSTEM: Windows.

[/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) был указан при построении приложения windows (Win32), в котором непосредственно использует один или несколько из следующих:

- kernel32.dll

- Gdi32.dll

- user32.dll

- один из необходимых компонентов msvcrt\* библиотеки DLL.

Устранить это предупреждение, не указывая **/SUBSYSTEM:NATIVE**.
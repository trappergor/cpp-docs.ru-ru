---
title: Предупреждение средств компоновщика LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 62ce0a0edc7f15bc5a19e4630133976f413da35a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352662"
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237

/SUBSYSTEM:NATIVE, указанный при импорте из «dll»; Используйте/SUBSYSTEM: Console или/SUBSYSTEM: Windows.

[/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) был указан при построении приложения windows (Win32), в котором непосредственно использует один или несколько из следующих:

- kernel32.dll

- gdi32.dll

- user32.dll

- один из необходимых компонентов msvcrt\* библиотеки DLL.

Устранить это предупреждение, не указывая **/SUBSYSTEM:NATIVE**.
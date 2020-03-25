---
title: Предупреждение средств компоновщика LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: aaa26393f1ce76d3e1bc40e5ba4978d1bcdb4fc9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193762"
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237

Указан/SUBSYSTEM: NATIVE при импорте из "DLL"; Используйте/SUBSYSTEM: CONSOLE или/SUBSYSTEM: WINDOWS.

Параметр [/SUBSYSTEM: Native](../../build/reference/subsystem-specify-subsystem.md) был указан при создании приложения Windows (Win32), которое непосредственно использует один или несколько следующих компонентов:

- kernel32.dll

- gdi32.dll

- user32.dll

- Одна из библиотек MSVCRT\*.

Устраните это предупреждение, не указывая **/SUBSYSTEM: Native**.

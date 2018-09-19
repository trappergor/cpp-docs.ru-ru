---
title: Предупреждение средств компоновщика LNK4237 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 479bd4ff8a4f48da679c9e17ec100668de84d089
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113712"
---
# <a name="linker-tools-warning-lnk4237"></a>Предупреждение средств компоновщика LNK4237

/SUBSYSTEM:NATIVE, указанный при импорте из «dll»; Используйте/SUBSYSTEM: Console или/SUBSYSTEM: Windows.

[/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) был указан при построении приложения windows (Win32), в котором непосредственно использует один или несколько из следующих:

- kernel32.dll

- Gdi32.dll

- user32.dll

- один из необходимых компонентов msvcrt\* библиотеки DLL.

Устранить это предупреждение, не указывая **/SUBSYSTEM:NATIVE**.
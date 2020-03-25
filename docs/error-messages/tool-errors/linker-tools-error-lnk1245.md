---
title: Ошибка средств компоновщика LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 19e3f820b5bd7fdd8eac2f7b5a96fb5923ae0b92
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183804"
---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245

указана недопустимая подсистема "подсистема". /SUBSYSTEM должен быть WINDOWS, WINDOWSCE или CONSOLE

[/CLR](../../build/reference/clr-common-language-runtime-compilation.md) использовался для компиляции объекта, и одно из следующих условий было истинно:

- Определена настраиваемая точка входа ([/entry](../../build/reference/entry-entry-point-symbol.md)), поэтому компоновщику не удалось определить подсистему.

- Значение было передано параметру компоновщика [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) , недопустимому для объектов/CLR.

В обоих случаях решением является указание допустимого значения для параметра компоновщика/SUBSYSTEM.

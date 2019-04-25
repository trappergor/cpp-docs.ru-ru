---
title: Ошибка средств компоновщика LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 4cf9a6c4356872b727a10a360396e51e38928b29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160566"
---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245

Недопустимая подсистема «подсистема» задан; / SUBSYSTEM должен быть WINDOWS, WINDOWSCE или CONSOLE

[/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) использовалась для компиляции объекта и одно из следующих условий верно:

- Точка добавления настраиваемой записи был определен ([/Entry](../../build/reference/entry-entry-point-symbol.md)), таким образом, что компоновщик не может повлиять на подсистему.

- Было передано значение [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметра компоновщика, который не является допустимым для/CLR объектов.

Для обоих случаев решением является указать допустимое значение для параметра компоновщика/SUBSYSTEM.
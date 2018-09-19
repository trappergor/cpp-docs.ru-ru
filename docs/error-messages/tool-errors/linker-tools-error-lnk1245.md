---
title: Ошибка средств компоновщика LNK1245 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef7bace5cec937399d7a2ed440e21b9b751f4141
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041796"
---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245

Недопустимая подсистема «подсистема» задан; / SUBSYSTEM должен быть WINDOWS, WINDOWSCE или CONSOLE

[/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) использовалась для компиляции объекта и одно из следующих условий верно:

- Точка добавления настраиваемой записи был определен ([/Entry](../../build/reference/entry-entry-point-symbol.md)), таким образом, что компоновщик не может повлиять на подсистему.

- Было передано значение [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметра компоновщика, который не является допустимым для/CLR объектов.

Для обоих случаев решением является указать допустимое значение для параметра компоновщика/SUBSYSTEM.
---
title: Предупреждение средств компоновщика LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: d9659b0cf372ff8ebc225b890fb68866872bb3d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194412"
---
# <a name="linker-tools-warning-lnk4001"></a>Предупреждение средств компоновщика LNK4001

не указаны объектные файлы. используемые библиотеки

Компоновщик передал один или несколько LIB-файлов, но не имеет OBJ-файлов.

Так как компоновщик не может получить доступ к информации в LIB-файле, к которой он может получить доступ в OBJ-файле, это предупреждение означает, что вам придется явно указать другие параметры компоновщика. Например, может потребоваться указать параметры [/Machine](../../build/reference/machine-specify-target-platform.md), [/out](../../build/reference/out-output-file-name.md)или [/entry](../../build/reference/entry-entry-point-symbol.md) .

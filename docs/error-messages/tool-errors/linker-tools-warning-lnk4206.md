---
title: Предупреждение средств компоновщика LNK4206 | Документы Microsoft
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0cb74776f307affb0455d972e27e594e6d06294
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4206"></a>Предупреждение средств компоновщика LNK4206

> сведения о предкомпилированном типе не найден. "*filename*" не скомпонован или перезаписан; компоновка объекта выполняется как при отсутствии отладочных данных

*Filename* объектный файл, скомпилированный с помощью [/Yc](../../build/reference/yc-create-precompiled-header-file.md), либо не был задан в команде LINK, либо был перезаписан.

Обычный сценарий для этого предупреждения — когда OBJ-файл, который был скомпилирован с параметром/Yc находится в библиотеке, и при этом отсутствуют символические ссылки данный OBJ-файл из кода.  В этом случае компоновщик не используется (и даже видеть) OBJ-файле.  В этом случае необходимо повторной компиляции кода и использовать [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) для объектов, скомпилированных с помощью [/Yu](../../build/reference/yu-use-precompiled-header-file.md).
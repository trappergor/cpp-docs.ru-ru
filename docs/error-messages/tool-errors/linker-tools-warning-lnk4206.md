---
title: "Предупреждение средств компоновщика LNK4206 | Документы Microsoft"
ms.date: 12/05/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd13ac59aefa074db869f0502743c7a49d23082c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4206"></a>Предупреждение средств компоновщика LNK4206

> сведения о предкомпилированном типе не найден. "*filename*" не скомпонован или перезаписан; компоновка объекта выполняется как при отсутствии отладочных данных

*Filename* объектный файл, скомпилированный с помощью [/Yc](../../build/reference/yc-create-precompiled-header-file.md), либо не был задан в команде LINK, либо был перезаписан.

Обычный сценарий для этого предупреждения — когда OBJ-файл, который был скомпилирован с параметром/Yc находится в библиотеке, и при этом отсутствуют символические ссылки данный OBJ-файл из кода.  В этом случае компоновщик не используется (и даже видеть) OBJ-файле.  В этом случае необходимо повторной компиляции кода и использовать [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) для объектов, скомпилированных с помощью [/Yu](../../build/reference/yu-use-precompiled-header-file.md).
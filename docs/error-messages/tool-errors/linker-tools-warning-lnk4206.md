---
title: Предупреждение средств компоновщика LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: dc81df89609f59834c8a3271dd64f3b99b281f90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613646"
---
# <a name="linker-tools-warning-lnk4206"></a>Предупреждение средств компоновщика LNK4206

> сведения о предкомпилированном типе не найден. "*filename*" не скомпонован или перезаписан; компоновка объекта выполняется как при отсутствии отладочных данных

*Filename* объектного файла, скомпилированного с помощью [/Yc](../../build/reference/yc-create-precompiled-header-file.md), либо не был задан в команде LINK или был перезаписан.

Распространенный сценарий для этого предупреждения — когда OBJ-файл, который был скомпилирован с параметром/Yc находится в библиотеке, и при этом не символ ссылки на данный OBJ-файл из кода.  В этом случае компоновщик будет не используется (или даже см. в разделе) OBJ-файле.  В этом случае необходимо перекомпилировать код и использовать [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) для объектов, скомпилированных с помощью [/Yu](../../build/reference/yu-use-precompiled-header-file.md).
---
title: RES-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
ms.openlocfilehash: 3cbddba1273d579454560f176df00b09b03c89bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575101"
---
# <a name="res-files-as-linker-input"></a>RES-файлы в качестве входных файлов компоновщика

При компоновке программы можно указать RES-файл. RES-файл создается компилятором ресурсов (RC). LINK автоматически преобразует RES-файлы в COFF. Средство CVTRES.exe должен быть в том же каталоге, что LINK.exe, или в каталоге, указанном в переменной среды PATH.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
---
title: . RES-файлы как входные данные компоновщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a6a572013a29420670a2aef8c91c9c4bc64e871
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706325"
---
# <a name="res-files-as-linker-input"></a>RES-файлы в качестве входных файлов компоновщика

При компоновке программы можно указать RES-файл. RES-файл создается компилятором ресурсов (RC). LINK автоматически преобразует RES-файлы в COFF. Средство CVTRES.exe должен быть в том же каталоге, что LINK.exe, или в каталоге, указанном в переменной среды PATH.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
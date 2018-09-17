---
title: . EXP-файлы как входные данные компоновщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4badc93f38d5ce76dcc294ad4ae216c8e3f6454c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724013"
---
# <a name="exp-files-as-linker-input"></a>EXP-файлы в качестве входных файлов компоновщика

Файлы экспорта (EXP) содержат сведения о экспортируемые элементы функции и данные. Когда LIB создает библиотеку импорта, она также создает файл EXP. EXP-файл используется при связывании это программа, которая экспортирует и импортирует из другой программы, прямо или косвенно. При компоновке с EXP-файл, LINK не создает библиотеку импорта, так как предполагается, что LIB уже создана. Дополнительные сведения о EXP-файлы и библиотеки импорта, см. в разделе [работа с библиотеками, импортировать и экспортировать файлы](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
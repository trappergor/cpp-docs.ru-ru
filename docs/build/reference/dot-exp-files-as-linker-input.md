---
title: EXP-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
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
ms.openlocfilehash: 170adfe54b34d14f84b54c717bc9f75fe0b7ab37
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418481"
---
# <a name="exp-files-as-linker-input"></a>EXP-файлы в качестве входных файлов компоновщика

Файлы экспорта (EXP) содержат сведения о экспортируемые элементы функции и данные. Когда LIB создает библиотеку импорта, она также создает файл EXP. EXP-файл используется при связывании это программа, которая экспортирует и импортирует из другой программы, прямо или косвенно. При компоновке с EXP-файл, LINK не создает библиотеку импорта, так как предполагается, что LIB уже создана. Дополнительные сведения о EXP-файлы и библиотеки импорта, см. в разделе [работа с библиотеками, импортировать и экспортировать файлы](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)

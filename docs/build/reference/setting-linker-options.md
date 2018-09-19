---
title: Настройка параметров компоновщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2fd99732c7f79b3c61ff5b31516b98a478ed4a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713080"
---
# <a name="setting-linker-options"></a>Настройка параметров компоновщика

Параметры компоновщика можно задать внутри или вне среды разработки. В этой статье для каждого параметра компоновщика рассматриваются, как его можно установить в среде разработки. См. в разделе [параметры компоновщика](../../build/reference/linker-options.md) полный список.

При выполнении ссылки вне среды разработки, можно указать входные данные в одной или несколькими способами:

- На [командной строки](../../build/reference/linker-command-line-syntax.md)

- С помощью [командные файлы](../../build/reference/link-command-files.md)

- В [переменные среды](../../build/reference/link-environment-variables.md)

ССЫЛКА первого обрабатывает параметры, заданные в переменной среды LINK, следуют параметры в том порядке, они указаны в командной строке и в командных файлах. Если параметр повторяется с различными аргументами, обработано последним имеет приоритет.

Параметры применяются ко всей сборки; параметры не могут применяться для определенных входных файлов.

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
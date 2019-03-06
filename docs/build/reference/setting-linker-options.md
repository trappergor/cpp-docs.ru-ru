---
title: Настройка параметров компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
ms.openlocfilehash: 61f4ee8d02cda5b2cd270d7ef789bf58060e7fdf
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423174"
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

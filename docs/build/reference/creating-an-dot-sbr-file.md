---
title: Создание SBR-файла
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 6a2e685d33b108ce542fdc6e3e0565cc37299c1c
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508745"
---
# <a name="creating-an-sbr-file"></a>Создание SBR-файла

> [!WARNING]
> Хотя средство BSCMAKE по-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки. Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF-файле SQL Server в папке решения.

Входные файлы для BSCMAKE, SBR-файлов. Компилятор создает SBR-файл для каждого файла объект (.obj), то компилируется. При сборке или обновить файл информации об все SBR-файлы для вашего проекта должно быть доступно на диске.

Чтобы создать SBR-файл с помощью сведений, укажите [/FR](fr-fr-create-dot-sbr-file.md).

Чтобы создать SBR-файл, в которых нет локальных символов, укажите [/Fr](fr-fr-create-dot-sbr-file.md). Если SBR-файлы содержат локальные символы, можно удалить их из BSC-файл с помощью BSCMAKE [параметр /El](bscmake-options.md)`.`

Можно создать SBR-файл, не выполняя полную компиляцию. Например можно указать параметр /Zs компилятору выполнить проверку синтаксиса и по-прежнему создавать SBR-файл, если указать /FR или/fr.

Процесс построения может быть более эффективным, если SBR-файлы сначала упаковать, чтобы удалить неиспользуемые определения. Компилятор автоматически упаковывает SBR-файлов.

## <a name="see-also"></a>См. также

[Сборка BSC-файла](building-a-dot-bsc-file.md)

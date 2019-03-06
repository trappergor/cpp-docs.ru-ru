---
title: Справочник ВSCMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 1dd89047b8fa6a415e7e19dd69ca3f499887299f
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416258"
---
# <a name="bscmake-reference"></a>Справочник ВSCMAKE

> [!WARNING]
> Хотя средство BSCMAKE по-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки. Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF-файле SQL Server в папке решения.

Служебная программа Microsoft Browse Information Maintenance (BSCMAKE.EXE) создает файл информации об исходном коде (BSC) из SBR-файлов, созданных во время компиляции. Некоторые сторонние средства используйте BSC-файлы для анализа кода.

При построении программы можно автоматически создать файл информации об исходном коде, используя программу BSCMAKE. Вам не требуется знать, как запускать BSCMAKE, если вы создаете файл информации об исходном коде в среде разработки Visual C++. Тем не менее можно прочитать этот раздел для понимания доступных возможностей.

При построении программы вне среды разработки вы по-прежнему можете создать пользовательский BSC-файл, который можно просмотреть в среде. Запустите BSCMAKE для SBR-файлов, созданных во время компиляции.

> [!NOTE]
>  Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

Этот раздел содержит следующие подразделы:

- [Создание файлов информации об исходном коде: обзор](../../build/reference/building-browse-information-files-overview.md)

- [Построение BSC-файла](../../build/reference/building-a-dot-bsc-file.md)

- [Командная строка BSCMAKE](../../build/reference/bscmake-command-line.md)

- [Командный файл BSCMAKE](../../build/reference/bscmake-command-file-response-file.md)

- [Параметры BSCMAKE](../../build/reference/bscmake-options.md)

- [Коды выхода BSCMAKE](../../build/reference/bscmake-exit-codes.md)

## <a name="see-also"></a>См. также

[Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)

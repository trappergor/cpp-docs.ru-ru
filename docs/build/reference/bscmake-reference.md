---
title: Справочник ВSCMAKE
ms.date: 05/06/2019
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 72ad297ee5a24bc0c7ffd3ed25959031d0b8a309
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220557"
---
# <a name="bscmake-reference"></a>Справочник ВSCMAKE

> [!WARNING]
> Хотя средство BSCMAKE по-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки. Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF-файле SQL Server в папке решения.

Служебная программа Microsoft Browse Information Maintenance (BSCMAKE.EXE) создает файл информации об исходном коде (BSC) из SBR-файлов, созданных во время компиляции. Некоторые сторонние средства используйте BSC-файлы для анализа кода.

При построении программы можно автоматически создать файл информации об исходном коде, используя программу BSCMAKE. Необходимо знать, как запускать BSCMAKE, если вы создаете файл информации об в среде разработки Visual Studio. Тем не менее можно прочитать этот раздел для понимания доступных возможностей.

При построении программы вне среды разработки вы по-прежнему можете создать пользовательский BSC-файл, который можно просмотреть в среде. Запустите BSCMAKE для SBR-файлов, созданных во время компиляции.

> [!NOTE]
>  Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

Этот раздел содержит следующие подразделы:

- [Создание файлов информации об исходном коде: обзор](building-browse-information-files-overview.md)

- [Построение BSC-файла](building-a-dot-bsc-file.md)

- [Командная строка BSCMAKE](bscmake-command-line.md)

- [Командный файл BSCMAKE](bscmake-command-file-response-file.md)

- [Параметры BSCMAKE](bscmake-options.md)

- [Коды выхода BSCMAKE](bscmake-exit-codes.md)

## <a name="see-also"></a>См. также

[Средства сборки дополнительных MSVC](c-cpp-build-tools.md)

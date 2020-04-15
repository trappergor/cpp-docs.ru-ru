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
ms.openlocfilehash: f95e34b9599de628463b9f92ebf8f01036237891
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320737"
---
# <a name="bscmake-reference"></a>Справочник ВSCMAKE

> [!WARNING]
> Хотя средство BSCMAKE по-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки. Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF-файле SQL Server в папке решения.

Служебная программа Microsoft Browse Information Maintenance (BSCMAKE.EXE) создает файл информации об исходном коде (BSC) из SBR-файлов, созданных во время компиляции. Некоторые сторонние инструменты используют файлы .bsc для анализа кода.

При построении программы можно автоматически создать файл информации об исходном коде, используя программу BSCMAKE. Вам не нужно знать, как запустить BSCMAKE, если вы создаете файл информации о просмотре в среде разработки Visual Studio. Тем не менее можно прочитать этот раздел для понимания доступных возможностей.

При построении программы вне среды разработки вы по-прежнему можете создать пользовательский BSC-файл, который можно просмотреть в среде. Запустите BSCMAKE для SBR-файлов, созданных во время компиляции.

> [!NOTE]
> Запустить этот инструмент можно только с запроса команды Visual Studio Developer. В системной командной строке или проводнике это невозможно.

В этом разделе рассматриваются следующие темы:

- [Информационные файлы просмотра сборки: общие сведения](building-browse-information-files-overview.md)

- [Создание файла .bsc](building-a-dot-bsc-file.md)

- [Командная строка BSCMAKE](bscmake-command-line.md)

- [Командный файл BSCMAKE](bscmake-command-file-response-file.md)

- [Варианты BSCMAKE](bscmake-options.md)

- [Коды выхода BSCMAKE](bscmake-exit-codes.md)

## <a name="see-also"></a>См. также раздел

[Дополнительные инструменты сборки MSVC](c-cpp-build-tools.md)

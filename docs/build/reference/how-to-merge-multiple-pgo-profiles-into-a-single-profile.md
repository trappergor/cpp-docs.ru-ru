---
title: 'Как: слияние нескольких профилей PGO в единый профиль | Документы Microsoft'
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca8fd6ef94af290d568f3186747c659b918c0fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Практическое руководство. Слияние нескольких профилей PGO в единый профиль

Профильная оптимизация (PGO) является мощный инструмент для создания оптимизированного двоичного кода, в зависимости от варианта, который выполняется профилирование. Но что делать, если у вас есть приложение, которое имеет несколько важных различных сценариев? Как создать единый профиль, профильной Оптимизации можно использовать из нескольких различных сценариях В Visual Studio, диспетчер профильной Оптимизации [pgomgr.exe](pgomgr.md), делает это задание.

Для объединения профилей используется синтаксис:

`pgomgr /merge[:num] [.pgc_files] .pgd_files`

где `num` — необязательный весовой коэффициент для PGC-файлы, добавленные в слиянии. Весовые коэффициенты обычно используются при наличии скриптов, которые являются более важной, чем другие, или если существуют сценарии, которые должны выполняться несколько раз.

> [!NOTE]
> Диспетчер профильной Оптимизации не работает с данными устаревших профиля. Чтобы объединить PGC-файл в PGD-файл, PGC-файл должен быть создан путем исполняемого файла, который был создан в одном вызове компоновки, что и PGD-файл.

## <a name="examples"></a>Примеры

В этом примере диспетчер профильной Оптимизации добавляет pgcFile.pgc файл pgdFile.pgd шесть раз:

`pgomgr /merge:6 pgcFile.pgc pgdFile.pgd`

В этом примере диспетчер профильной Оптимизации добавляет pgcFile1.pgc и pgcFile2.pgc в файл pgdFile.pgd дважды для каждого PGC-файл.

`pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd`

Если диспетчер профильной Оптимизации выполняется без аргументов файл .pgc, он выполняет локальный каталог для всех файлов, имеющих то же базовое имя, как PGD-файла, за которым следует восклицательный знак (!) и выберите один или несколько произвольные символы. Например, если локальный каталог содержит файлы test.pgd, test!1.pgc, test2.pgc и test!hello.pgc и следующая команда запускается из локального каталога, затем **pgomgr** объединяются test.pgd test!1.pgc и test!hello.pgc.

`pgomgr /merge test.pgd`

## <a name="see-also"></a>См. также

[Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)

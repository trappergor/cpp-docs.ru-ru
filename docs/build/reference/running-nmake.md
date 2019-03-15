---
title: Запуск программы NMAKE
ms.date: 09/05/2018
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: dac5e9c1676278d150dd9802697a8ae8959a40e5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827483"
---
# <a name="running-nmake"></a>Запуск программы NMAKE

## <a name="syntax"></a>Синтаксис

> **NMAKE** [*параметр* ...] [*макросы* ...] [*целевых объектов* ...] [**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>Примечания

Только указанные сборки NMAKE *целевых объектов* или, если он не задан, первый для целевых платформ в файле makefile. Первый целевой объект файла makefile может быть [псевдоцелью](pseudotargets.md) , создающим другие целевые объекты. Программа NMAKE использует файлы makefile, указанный в параметре /F; Если /F не указан, используется файл Makefile в текущем каталоге. Если указан файл makefile, он использует правила вывода для построения командной строки *целевых объектов*.

*Commandfile* текстовый файл (или файл ответов) содержит входные данные командной строки. Другие входные данные могут указываться перед или после \@ *commandfile*. Путь разрешается. В *commandfile*, разрывы строк обрабатываются как пробелы. Определения макросов следует заключите в кавычки, если они содержат пробелы.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Параметры NMAKE](nmake-options.md)

[Tools.ini и NMAKE](tools-ini-and-nmake.md)

[Коды выхода из NMAKE](exit-codes-from-nmake.md)

## <a name="see-also"></a>См. также

[Справочник по программе NMAKE](nmake-reference.md)

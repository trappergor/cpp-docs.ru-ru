---
title: Создание манифеста в командной строке | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eaaebf02299f8f3907012ec97e467d137cbd246b
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315487"
---
# <a name="manifest-generation-at-the-command-line"></a>Создание манифеста в командной строке

При создании приложений C/C++ из командной строки с помощью nmake или аналогичных средств, манифест создается после компоновщик после обработки всех объектных файлов и построен конечный двоичный файл. Компоновщик собирает сведения о сборке, хранящиеся в файлах объектов и объединяет эту информацию в конечный файл манифеста. По умолчанию компоновщик создает файл с именем *имя_двоичного_файла*. *расширение*.manifest для описания конечный двоичный файл. Компоновщик не внедряет файл манифеста в двоичный файл и можно создавать только манифест в виде внешнего файла. Существует несколько способов для внедрения манифеста в конечный двоичный файл, например с помощью [инструмента манифеста (mt.exe)](https://msdn.microsoft.com/library/aa375649) или компиляции манифест в файл ресурсов. Очень важно Имейте в виду, что определенные правила нужно соблюдать при внедрении манифеста в конечный двоичный файл, чтобы включить такие функции, как инкрементную компоновку, подписи, изменить и продолжить. Эти и другие возможности рассматриваются в [как: внедрить манифест в приложения C/C++](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) при построении в командной строке.

## <a name="see-also"></a>См. также

[Манифесты](https://msdn.microsoft.com/library/aa375365)<br/>
[/INCREMENTAL (инкрементное связывание)](../build/reference/incremental-link-incrementally.md)<br/>
[Сборки со строгими именами (подписывание сборок) (C++-CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Изменить и продолжить](/visualstudio/debugger/edit-and-continue)<br/>
[Основные сведения о создании манифестов для программ на C/C++](../build/understanding-manifest-generation-for-c-cpp-programs.md)<br/>

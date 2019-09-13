---
title: Создание манифеста в командной строке
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
ms.openlocfilehash: 381406213422e286dd9aba26adcdbd6caff7bfe3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493194"
---
# <a name="manifest-generation-at-the-command-line"></a>Создание манифеста в командной строке

При сборке C/C++ Applications из командной строки с помощью NMAKE или аналогичных средств манифест создается после того, как компоновщик обработает все объектные файлы и создал окончательный двоичный файл. Компоновщик собирает сведения о сборке, хранящиеся в объектных файлах, и объединяет эту информацию в окончательный файл манифеста. По умолчанию компоновщик создаст файл с именем *binary_name*. *расширение*manifest для описания конечного двоичного файла. Компоновщик не внедряет файл манифеста внутри двоичного файла и может создать манифест только как внешний файл. Существует несколько способов внедрения манифеста в конечный двоичный файл, например с помощью [средства манифеста (Mt. exe)](/windows/win32/sbscs/mt-exe) или компиляции манифеста в файле ресурсов. Важно помнить, что при внедрении манифеста в окончательный двоичный файл необходимо соблюдать определенные правила, чтобы включить такие функции, как добавочная компоновка, подписывание и редактирование и продолжение. Эти и другие параметры обсуждаются в [разделе как: Внедрите манифест в C/C++ приложение](how-to-embed-a-manifest-inside-a-c-cpp-application.md) при сборке в командной строке.

## <a name="see-also"></a>См. также

[Манифесты](/windows/win32/sbscs/manifests)<br/>
[/INCREMENTAL (инкрементное связывание)](reference/incremental-link-incrementally.md)<br/>
[Сборки со строгими именами (подписывание сборок) (C++-CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)<br/>
[Изменить и продолжить](/visualstudio/debugger/edit-and-continue)<br/>
[Основные сведения о создании манифестов для программ на C/C++](understanding-manifest-generation-for-c-cpp-programs.md)<br/>

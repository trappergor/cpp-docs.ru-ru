---
title: 'Стандартных файлы для просмотра информации: Общие сведения о | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 493f25ba6839058a9ff749cb0dbb3853b1b16494
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712300"
---
# <a name="building-browse-information-files-overview"></a>Информационные файлы просмотра сборки: общие сведения

Чтобы создать просмотра для просмотра символов, компилятор создает SBR-файл для каждого исходного файла в проекте, а затем BSCMAKE. EXE Сцепляет SBR-файлов в один файл BSC-файл.

Создание SBR и BSC файлов занимает некоторое время, поэтому Visual C++ эти функции будут отключены по умолчанию. Если вы хотите просмотреть текущую информацию, необходимо включить параметры просмотра и повторите сборку проекта.

Используйте [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) или [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) сообщить компилятору создать SBR-файлов. Чтобы создать файл BSC, можно вызвать [BSCMAKE](../../build/reference/bscmake-command-line.md) из командной строки. Использование BSCMAKE из командной строки позволяет более точно контролировать манипуляции файлы для просмотра информации. См. в разделе [Справочник по BSCMAKE](../../build/reference/bscmake-reference.md) Дополнительные сведения.

> [!TIP]
>  Можно включить создание SBR-файла, но оставить отключить создание BSC-файла. Это обеспечивает быстрые построения, а также позволяет быстро создавать новый BSC-файла, включение Создание BSC-файла и сборка проекта.

Можно уменьшить время, память и дисковое пространство, необходимое для создания BSC-файла, уменьшив размер BSC-файла.

См. в разделе [свойств "Общие" (проект)](../../ide/general-property-page-project.md) сведения о том, как создать файл обозревателя в среде разработки.

### <a name="to-create-a-smaller-bsc-file"></a>Для создания небольших BSC-файла

1. Используйте [командной строки параметры BSCMAKE](../../build/reference/bscmake-options.md) исключить данные из файла для просмотра информации.

1. Не включайте локальные символы в один или несколько SBR-файлов при компиляции или сборке.

1. Если объектный файл не содержит сведения, необходимые для текущего этапа отладки, не указывать его SBR-файл из команды BSCMAKE при перестроении файла для просмотра информации.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Для объединения информации обзора из нескольких проектов в один файл обозревателя (BSC-файл)

1. Не построения BSC-файл на уровне проекта либо предотвратить усечение SBR-файлов с помощью параметра /n.

1. После все проекты построены, запустите BSCMAKE со всеми SBR-файлов в качестве входных данных. Допускаются подстановочные знаки. К примеру, если каталоги проектов C:\X C:\Y и C:\Z с SBR-файлы в их и вы хотите получать объединить все в один файл BSC-файл, затем использовать BSCMAKE C:\X\\\*.sbr C:\Y\\\*.sbr C:\Z\\ \*c:\whatever_directory\combined.bsc /o .sbr для построения объединенных BSC-файле.

## <a name="see-also"></a>См. также

[Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)<br/>
[Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)

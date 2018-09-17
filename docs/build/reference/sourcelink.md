---
title: / SOURCELINK (Sourcelink включить файл в PDB-ФАЙЛ) | Документация Майкрософт
ms.custom: ''
ms.date: 08/20/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /sourcelink
dev_langs:
- C++
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dff53f7a4db12e32bca2494ba99f5b3b8203d48f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706671"
---
# <a name="sourcelink-include-sourcelink-file-in-pdb"></a>/ SOURCELINK (Sourcelink включить файл в PDB-ФАЙЛ)

Указывает файл конфигурации SourceLink для включения в PDB-файла компоновщиком.

## <a name="syntax"></a>Синтаксис

> **/ SOURCELINK:**_имя файла_

## <a name="arguments"></a>Аргументы

*filename*<br/>
Задает конфигурации в формате JSON файл, содержащий простое сопоставление локальных путей для URL-адреса приложения откуда можно извлечь исходный файл для отображения в отладчике. Дополнительные сведения о формате этого файла см. в разделе [исходной схемы JSON ссылку](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema).

## <a name="remarks"></a>Примечания

SourceLink — система зависит от языка - и системы управления версиями для предоставления отладки исходного кода для двоичных файлов. SourceLink поддерживается начиная с Visual Studio 2017 версии 15.8 двоичные файлы машинного кода C++. Обзор SourceLink, см. в разделе [ссылки на источник](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md). Сведения об использовании SourceLink в проектах и как для создания файла SourceLink как часть проекта, см. в разделе [SourceLink с помощью](https://github.com/dotnet/sourcelink#using-sourcelink).

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Установка параметра компоновщика /SOURCELINK в Visual Studio

1. Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры** , добавьте **/SOURCELINK:**_filename_ и выберите **ОК** или **применить**для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Этот параметр не поддерживает программный эквивалент.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)

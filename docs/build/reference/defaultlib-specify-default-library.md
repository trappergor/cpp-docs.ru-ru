---
title: / DEFAULTLIB (определение библиотеки по умолчанию) | Документы Microsoft
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9afcaa0e229ec34ba91b4d60a7a4fa9acec2d7e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569785"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (определение библиотеки по умолчанию)

Указание библиотеки по умолчанию для поиска для разрешения внешних ссылок.

## <a name="syntax"></a>Синтаксис

> **/ DEFAULTLIB**:_библиотеки_

### <a name="arguments"></a>Аргументы

|Аргумент|Описание:|
|-|-|
*Библиотека*|Имя библиотеки для поиска при разрешении внешних ссылок.

## <a name="remarks"></a>Примечания

**/DEFAULTLIB** параметр добавляет один *библиотеки* в список библиотек, LINK выполняет поиск при разрешении ссылок. Это библиотека, заданная с помощью **/DEFAULTLIB** выполняется после библиотек, явно указанных в командной строке и перед стандартных библиотек в OBJ-файлы.

При использовании без аргументов, [/NODEFAULTLIB (игнорировать все стандартные библиотеки)](../../build/reference/nodefaultlib-ignore-libraries.md) параметр переопределяет все **/DEFAULTLIB**:*библиотеки* параметры. **/NODEFAULTLIB**:*библиотеки* параметр переопределения **/DEFAULTLIB**:*библиотеки* при же *библиотеки*указано как имя.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите **/DEFAULTLIB**:*библиотеки* параметр для каждой библиотеки для поиска. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)

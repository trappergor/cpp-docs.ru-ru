---
title: /DEFAULTLIB (определение библиотеки по умолчанию)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 59a4b48e412cee6b2a90608747aa6fb3e1b79ca7
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326390"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (определение библиотеки по умолчанию)

Определение библиотеки по умолчанию для поиска для разрешения внешних ссылок.

## <a name="syntax"></a>Синтаксис

> **/ DEFAULTLIB**:_библиотеки_

### <a name="arguments"></a>Аргументы

*Библиотека*<br/>
Имя библиотеки для поиска при разрешении внешних ссылок.

## <a name="remarks"></a>Примечания

**/DEFAULTLIB** параметр добавляет один *библиотеки* в список библиотек, LINK выполняет поиск при разрешении ссылок. Это библиотека, заданная с помощью **/DEFAULTLIB** выполняется после библиотеки указаны явно в командной строке и перед стандартных библиотек в OBJ-файлы.

При использовании без аргументов, [/NODEFAULTLIB (игнорировать все стандартные библиотеки)](../../build/reference/nodefaultlib-ignore-libraries.md) параметр переопределяет все **/DEFAULTLIB**:*библиотеки* параметры. **/NODEFAULTLIB**:*библиотеки* параметр переопределения **/DEFAULTLIB**:*библиотеки* при же *библиотеки*имя указано в обоих.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите **/DEFAULTLIB**:*библиотеки* параметр для каждой библиотеки для поиска. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)

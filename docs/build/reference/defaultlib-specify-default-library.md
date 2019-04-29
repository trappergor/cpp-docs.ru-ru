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
ms.openlocfilehash: 0b7d4569c7be70bd97094ebbe09a7ae462331983
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293866"
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

При использовании без аргументов, [/NODEFAULTLIB (игнорировать все стандартные библиотеки)](nodefaultlib-ignore-libraries.md) параметр переопределяет все **/DEFAULTLIB**:*библиотеки* параметры. **/NODEFAULTLIB**:*библиотеки* параметр переопределения **/DEFAULTLIB**:*библиотеки* при же *библиотеки*имя указано в обоих.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите **/DEFAULTLIB**:*библиотеки* параметр для каждой библиотеки для поиска. Выберите **ОК** для сохранения внесенных изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)

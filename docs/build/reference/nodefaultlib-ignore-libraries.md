---
title: Параметр /NODEFAULTLIB (пропуск библиотек)
ms.date: 03/26/2019
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: 24528eb4c387c4cd0921ab089370d72b076ad640
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508758"
---
# <a name="nodefaultlib-ignore-libraries"></a>Параметр /NODEFAULTLIB (пропуск библиотек)

> **/ NODEFAULTLIB**[__:__*библиотеки*]

## <a name="arguments"></a>Аргументы

*Библиотека*<br/>
Библиотека, требуется, чтобы компоновщик не учитывает при разрешении внешних ссылок.

## <a name="remarks"></a>Примечания

Параметр/NODEFAULTLIB предписывает компоновщику удалить один или несколько стандартных библиотек из списка библиотек, в которой выполняется поиск при разрешении внешних ссылок.

Чтобы создать OBJ-файле, который не содержит ссылок на библиотеки по умолчанию, используйте [/Zl (Omit Default Library Name)](zl-omit-default-library-name.md).

По умолчанию параметр/NODEFAULTLIB удаляет все стандартные библиотеки из списка библиотек, в которой выполняется поиск при разрешении внешних ссылок. Необязательный *библиотеки* параметр позволяет удалить указанную библиотеку из списка библиотек, он выполняет поиск при разрешении внешних ссылок. Укажите один параметр/NODEFAULTLIB для каждой библиотеки, которые вы хотите исключить.

Компоновщик разрешает ссылки на внешние определения поиск сначала в библиотеках, которые явно не указан, то по умолчанию библиотеки задано с помощью [/DEFAULTLIB:](defaultlib-specify-default-library.md) параметр, а затем по умолчанию библиотек в OBJ-файл файлы.

/ NODEFAULTLIB:*библиотеки* переопределяет/DEFAULTLIB:*библиотеки* при же *библиотеки* имя указано в обоих.

Если используется параметр/NODEFAULTLIB для сборки программы без библиотеки времени выполнения C, необходимо также использовать [/Entry](entry-entry-point-symbol.md) для указания точки входа функции в программе. Дополнительные сведения см. в разделе [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **ввода** страницу свойств.

1. Выберите **игнорировать все стандартные библиотеки** свойство. Также можно указать разделенный точками с запятой список библиотек, нужно учитывать в **игнорировать определенные стандартные библиотеки** свойство. **Командной строки** страница свойств показывает эффект от изменения, внесенные в эти свойства.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)

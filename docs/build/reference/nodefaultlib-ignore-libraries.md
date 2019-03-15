---
title: Параметр /NODEFAULTLIB (пропуск библиотек)
ms.date: 11/04/2016
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
ms.openlocfilehash: cacc1ef312065da5d6e62ddba1040e87fae9d709
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807459"
---
# <a name="nodefaultlib-ignore-libraries"></a>Параметр /NODEFAULTLIB (пропуск библиотек)

```
/NODEFAULTLIB[:library]
```

## <a name="arguments"></a>Аргументы

*Библиотека*<br/>
Библиотека, требуется, чтобы компоновщик не учитывает при разрешении внешних ссылок.

## <a name="remarks"></a>Примечания

Параметр/NODEFAULTLIB предписывает компоновщику удалить один или несколько стандартных библиотек из списка библиотек, в которой выполняется поиск при разрешении внешних ссылок.

Чтобы создать OBJ-файле, который не содержит ссылки на библиотеки по умолчанию, используйте [/Zl (Omit Default Library Name)](zl-omit-default-library-name.md).

По умолчанию параметр/NODEFAULTLIB удаляет все стандартные библиотеки из списка библиотек, в которой выполняется поиск при разрешении внешних ссылок. Необязательный *библиотеки* параметр позволяет удалить указанных библиотек из списка библиотек, он выполняет поиск при разрешении внешних ссылок. Укажите один параметр/NODEFAULTLIB для каждой библиотеки, которые вы хотите исключить.

Компоновщик разрешает ссылки на внешние определения поиск сначала в библиотеках, которые были явно указаны, а затем по умолчанию библиотек, указанных с помощью параметра/DEFAULTLIB, а затем в стандартных библиотек в OBJ-файлы.

/ NODEFAULTLIB:*библиотеки* переопределяет [/DEFAULTLIB:](defaultlib-specify-default-library.md)*библиотеки* при же *библиотеки* имя указано в обоих.

Если используется параметр/NODEFAULTLIB, например, для построения программы без библиотеки времени выполнения C, необходимо также использовать [/Entry](entry-entry-point-symbol.md) для указания точки входа (функции) в программе. Дополнительные сведения см. в разделе [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода**страницу свойств.

1. Выберите **игнорировать все стандартные библиотеки** свойства или указать список библиотек, которые нужно учитывать в **Игнорировать указанную библиотеку** свойство. **Командной строки** страницу свойств будет Показать эффект изменения, внесенные в эти свойства.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>См. также

[Справочник по MSVC компоновщика](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)

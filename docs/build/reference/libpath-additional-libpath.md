---
title: Параметр /LIBPATH (дополнительный параметр libpath)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: ab586c788825a854e7d3cb3760da6e4e5558de3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269219"
---
# <a name="libpath-additional-libpath"></a>Параметр /LIBPATH (дополнительный параметр libpath)

```
/LIBPATH:dir
```

## <a name="parameters"></a>Параметры

*dir*<br/>
Указывает путь, компоновщик будет поиска, затем путь, указанный в параметре среды LIB.

## <a name="remarks"></a>Примечания

Параметр/LIBPATH переопределять путь окружения библиотеки. Компоновщик сначала попытайтесь найти в каталоге, указанном этим параметром и выполните поиск в каталоге, указанном в переменной среды LIB. Можно указать только один каталог для каждого вводимого параметра/LIBPATH. Если вы хотите указать несколько каталогов, необходимо указать несколько параметров/LIBPATH. Поиска указанные папки в порядке.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **Дополнительные каталоги библиотек** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)

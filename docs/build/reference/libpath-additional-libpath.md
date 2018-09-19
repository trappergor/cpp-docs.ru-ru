---
title: -LIBPATH (дополнительный параметр Libpath) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 784281df23b0a8d43625766297b6cbbd20179c14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717201"
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

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **Дополнительные каталоги библиотек** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
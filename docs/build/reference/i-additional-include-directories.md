---
title: -I (Дополнительные каталоги включаемых файлов) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a580488650a1272ec1dffcd1f0ba27c736df92da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705345"
---
# <a name="i-additional-include-directories"></a>/I (дополнительные каталоги включения)

Добавляет каталог к списку каталогов для поиска включаемых файлов.

## <a name="syntax"></a>Синтаксис

```
/I[ ]directory
```

## <a name="arguments"></a>Аргументы

*Каталог*<br/>
Каталог для добавления в список каталогов для поиска включаемых файлов.

## <a name="remarks"></a>Примечания

Чтобы добавить несколько каталогов, используйте этот параметр несколько раз. Поиск каталогов выполняется только в том случае, пока не будет найден указанного включаемого файла.

Этот параметр можно использовать с отклонение стандартных путей включения ([/X (отклонение стандартных путей включения)](../../build/reference/x-ignore-standard-include-paths.md)) параметр.

Компилятор выполняет поиск каталогов в следующем порядке:

1. Каталоги, содержащие исходный файл.

1. Каталоги, указанные с помощью **/I** параметр, в том порядке, в котором их находит CL.

1. Каталоги, указанные в **INCLUDE** переменной среды.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **Дополнительные каталоги включаемых файлов** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Пример

Следующая команда выполняет поиск включаемых файлов, запрашиваемые MAIN.c в следующем порядке: сначала в каталоге, содержащем MAIN.c, затем в каталоге \INCLUDE, а затем в каталоге \MY\INCLUDE и наконец в каталогах, назначенных для ВКЛЮЧЕНИЯ переменная среды.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
---
title: -bigobj (увеличение числа разделов в. OBJ-файл) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bigobj
dev_langs:
- C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f10456bea8be552df42efe135818ac9c47393fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721491"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Увеличение количества разделов в OBJ-файле)

**/ bigobj** увеличивает число разделов, которые могут содержать объектный файл.

## <a name="syntax"></a>Синтаксис

```
/bigobj
```

## <a name="remarks"></a>Примечания

По умолчанию объектный файл может содержать до 65 536 (2 ^ 16) адресуемых секций. Это происходит, независимо от того, что целевая платформа указывается. **/ bigobj** увеличивает его адрес емкость до 4 294 967 296 (2 ^ 32).

Большинство модулей никогда не создаст OBJ-файл, содержащий более чем 65 536 разделах. Тем не менее машины созданный код или код, усложняет использование библиотеки шаблонов может потребоваться OBJ-файлы, которые могут содержать дополнительные разделы. **/ bigobj** включена по умолчанию в проектах универсальной платформы Windows (UWP), так как автоматически сгенерированный код XAML содержит большое количество заголовков. Если вы отключаете этот параметр на проект приложения UWP вы, скорее всего возникает ошибка компилятора C1128.

Компоновщики, входящие в до Visual C++ 2005 не удается прочитать OBJ-файлы, которые были созданы с помощью **/bigobj**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
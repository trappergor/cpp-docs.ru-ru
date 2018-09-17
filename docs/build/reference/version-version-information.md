---
title: -VERSION (сведения о версии) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs:
- C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de2d7e3988c2e0024c4b0a668960bccfcf3dd2ae
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720893"
---
# <a name="version-version-information"></a>/VERSION (Сведения о версии)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Аргументы

*Основные* и *дополнительный номер*<br/>
Номер версии в заголовке файла .exe или .dll.

## <a name="remarks"></a>Примечания

Параметр / Version предписывает компоновщику поставить номер версии в заголовке файла .exe или .dll. Использование служебной программы DUMPBIN [/Headers](../../build/reference/headers.md) для просмотра поля OPTIONAL HEADER VALUES, чтобы увидеть соответствующий эффект/Version версии образа.

*Основных* и *незначительные* аргументами являются десятичные числа в диапазоне от 0 до 65 535. По умолчанию используется версия 0.0.

Сведения, указанные с помощью/Version не влияет на сведения о версии, который отображается для приложения при просмотре его свойства в проводнике. Сведения о версии поступают из файла ресурсов, который используется для построения приложения. См. в разделе [редактор сведений о версии](../../windows/version-information-editor.md) Дополнительные сведения.

Другой способ добавить номер версии — с помощью [версии](../../build/reference/version-c-cpp.md) оператор определения модуля.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Общие** страницу свойств.

1. Изменить **версии** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
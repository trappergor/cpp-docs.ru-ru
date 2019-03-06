---
title: /FIXED (фиксированный базовый адрес)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: ccb89b7dfed78ddebf73aaf6e2a1a8529b065042
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423044"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (фиксированный базовый адрес)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Примечания

Указывает операционной системе загружать программу только по ее предпочтительному базовому адресу. Если предпочтительный базовый адрес недоступен, операционная система не загружается файл. Дополнительные сведения см. в разделе [Параметр /Base (базовый адрес)](../../build/reference/base-base-address.md).

Компоновщике значение по умолчанию для библиотеки DLL, а параметр/FIXED — по умолчанию для любого другого типа проекта.

Если указан параметр/fixed, LINK не создает в программе секцию перемещения. Во время выполнения Если операционная система не может загрузить программу по указанному адресу, он выводит сообщение об ошибке и программа не загружается.

Укажите компоновщике для создания в программе секцию перемещения.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **командной строки** страницу свойств.

1. Введите имя параметра и задав в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)

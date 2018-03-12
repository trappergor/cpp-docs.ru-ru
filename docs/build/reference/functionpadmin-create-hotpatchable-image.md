---
title: "/ FUNCTIONPADMIN (создать образ с обновлениями) | Документы Microsoft"
ms.custom: 
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c941ec7f0e94ba03979c914ddd26b8bd21237369
ms.sourcegitcommit: eb246547c7c9adc7d7ac4083ef09bf6e54dec914
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (создание образа, допускающего горячее обновление)

Готовит образ к оперативному исправлению.

## <a name="syntax"></a>Синтаксис

> **/FUNCTIONPADMIN**[**:**_space_]  

### <a name="arguments"></a>Аргументы

*space*<br/>
Количество битов разреживания Добавление в начале каждой функции в байтах. На x86 по умолчанию используется 5 байт заполнения, и на x64 по умолчанию используется 6 байт. Для других целевых объектов должно быть указано значение.

## <a name="remarks"></a>Примечания

Чтобы компоновщику создать образ с обновлениями, OBJ-файлы, должны компилироваться с [/hotpatch (создать образ с обновлениями)](../../build/reference/hotpatch-create-hotpatchable-image.md).

При компиляции и компоновки образа с одного вызова рабочей cl.exe, **/hotpatch** подразумевает **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите **/FUNCTIONPADMIN** в диалоговом окне **Дополнительные параметры**. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)

---
title: / FUNCTIONPADMIN (создать образ с обновлениями) | Документы Microsoft
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: d0a5ecfcc336e198de0adcc2393f740072d70cae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376758"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (создание образа, допускающего горячее обновление)

Готовит образ к оперативному исправлению.

## <a name="syntax"></a>Синтаксис

> **/ FUNCTIONPADMIN**[**:**_пространства_]  

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

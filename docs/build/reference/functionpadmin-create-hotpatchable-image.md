---
title: / FUNCTIONPADMIN (Создание образа, допускающего Оперативное обновление) | Документация Майкрософт
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
ms.openlocfilehash: 7a82611c453a96e9247e414d6adb777c07320482
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703993"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (создание образа, допускающего горячее обновление)

Готовит образ к оперативному исправлению.

## <a name="syntax"></a>Синтаксис

> **/ FUNCTIONPADMIN**[**:**_пространства_]

### <a name="arguments"></a>Аргументы

*space*<br/>
Объем пространства, добавляемый в начало каждой функции в байтах. На x86 по умолчанию используется 5 байт заполнения, и в x64 по умолчанию используется до 6 байт. Для других целевых объектов должно быть указано значение.

## <a name="remarks"></a>Примечания

Чтобы компоновщик для создания образа с обновлением, OBJ-файлов, должны компилироваться с [/hotpatch (создать образ с обновлениями)](../../build/reference/hotpatch-create-hotpatchable-image.md).

После компиляции и связать изображение с однократного вызова cl.exe, **/hotpatch** подразумевает **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите **/FUNCTIONPADMIN** в диалоговом окне **Дополнительные параметры**. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)

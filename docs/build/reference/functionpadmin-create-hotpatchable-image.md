---
title: /FUNCTIONPADMIN (создание образа, допускающего горячее обновление)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: 699da3cea9914b5a10bdf769015d41c33936a902
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818626"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (создание образа, допускающего горячее обновление)

Готовит образ к оперативному исправлению.

## <a name="syntax"></a>Синтаксис

> **/ FUNCTIONPADMIN**[**:**_пространства_]

### <a name="arguments"></a>Аргументы

*space*<br/>
Объем пространства, добавляемый в начало каждой функции в байтах. На x86 по умолчанию используется 5 байт заполнения, и в x64 по умолчанию используется до 6 байт. Для других целевых объектов должно быть указано значение.

## <a name="remarks"></a>Примечания

Чтобы компоновщик для создания образа с обновлением, OBJ-файлов, должны компилироваться с [/hotpatch (создать образ с обновлениями)](hotpatch-create-hotpatchable-image.md).

После компиляции и связать изображение с однократного вызова cl.exe, **/hotpatch** подразумевает **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Введите **/FUNCTIONPADMIN** в диалоговом окне **Дополнительные параметры**. Выберите **ОК** для сохранения внесенных изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)

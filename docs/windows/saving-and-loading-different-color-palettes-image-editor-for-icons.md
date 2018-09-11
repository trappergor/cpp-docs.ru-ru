---
title: Сохранение и загрузка различных цветовых палитр (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ac4a7f23e6f37891851740ed65356d7d2bec3c0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593627"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Сохранение и загрузка различных цветовых палитр (редактор изображений для значков)

Можно сохранять и загружать **цвета** палитру, которая содержит [настраивать цвета](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (По умолчанию **цвета** последняя использованная палитра автоматически загружается при запуске Visual Studio.)

> [!TIP]
> Так как **изображение** редактор имеет отсутствуют средства для восстановления по умолчанию **цвета** палитры, следует сохранить значение по умолчанию **цвета** палитру под именем, например  *Standard.PAL* или *default.pal* таким образом, можно легко восстановить параметры по умолчанию.

### <a name="to-save-a-custom-colors-palette"></a>Сохранение пользовательской палитры цветов

1. Из **изображение** меню, выберите **сохранить палитру**.

2. Перейдите в каталог, в который требуется сохранить палитру, и введите имя палитры.

3. Нажмите кнопку **Сохранить**.

### <a name="to-load-a-custom-colors-palette"></a>Загрузка пользовательской палитры цветов

1. Из **изображение** меню, выберите **Загрузка палитры**.

2. В [Загрузка палитры цветов-диалоговое окно](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), перейдите в нужный каталог и выберите палитру, которую нужно загрузить. **Цвет** палитры сохраняются с расширением PAL.

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  
[Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)
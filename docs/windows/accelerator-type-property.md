---
title: Свойство типа сочетания клавиш (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
ms.openlocfilehash: 00699f31b821aa508feec9ffe062d768f27ee5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475595"
---
# <a name="accelerator-type-property-c"></a>Свойство типа сочетания клавиш (C++)

Сочетания клавиш **тип** определяет, является ли сочетание клавиш, связанных с Идентификатором accelerator виртуального сочетание клавиш или значением ключа ASCII/ANSI:

- Если **тип** свойство является ASCII, [модификатор](../windows/accelerator-modifier-property.md) может быть только `None` или `Alt`, или он может содержать сочетание **Ctrl** ключа (как указано в перед клавишей `^`).

- Если **тип** свойство является VIRTKEY, любое сочетание `Modifier` и `Key` значения является допустимым.

   > [!NOTE]
   > Если вы хотите ввести значение в таблице сочетаний клавиш и имеют значение рассматриваться как ASCII/ANSI, просто щелкните **типа** для записи в таблице и выберите ASCII из раскрывающегося списка. Тем не менее если вы используете **сочетания клавиш** команды (**изменить** меню) для указания `Key`, необходимо изменить **тип** свойство от VIRTKEY до ASCII *перед* ввода `Key` кода.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Задание свойств сочетаний клавиш](../windows/setting-accelerator-properties.md)<br/>
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
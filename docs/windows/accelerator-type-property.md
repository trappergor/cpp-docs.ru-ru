---
title: Свойство типа сочетания клавиш (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b0d02ab8dfec7b6a3f286b09daf9797d62f0990
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384771"
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
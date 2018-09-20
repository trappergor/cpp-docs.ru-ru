---
title: Привязка сочетания клавиш к пункту меню (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: 15087bdd-3481-4ea9-9481-49f31845be70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f63a29e416a0b3331cdc9e5a2153435d765aaa0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407732"
---
# <a name="associating-an-accelerator-key-with-a-menu-item-c"></a>Привязка сочетания клавиш к пункту меню (C++)

Во многих случаях требуется, чтобы пункт меню и сочетание клавиш выдавали одну и ту же команду. Это делается путем назначения одного и того же идентификатора ресурса (ID) пункту меню и записи в таблице сочетаний клавиш приложения. Затем можно изменить заголовок пункта меню, чтобы показать имя сочетания клавиш. Дополнительные сведения о пунктах меню и сочетаний клавиш см. в разделе [связывание пункта меню с сочетанием клавиш](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сочетаний клавиш](../windows/accelerator-editor.md)<br/>
[Редакторы ресурсов](../windows/resource-editors.md)
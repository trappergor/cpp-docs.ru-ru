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
ms.openlocfilehash: 096658359ba46744a233d73bba52823dd9997841
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315734"
---
# <a name="associating-an-accelerator-key-with-a-menu-item-c"></a>Привязка сочетания клавиш к пункту меню (C++)

Во многих случаях требуется, чтобы пункт меню и сочетание клавиш выдавали одну и ту же команду. Это делается путем назначения одного и того же идентификатора ресурса (ID) пункту меню и записи в таблице сочетаний клавиш приложения. Затем можно изменить заголовок пункта меню, чтобы показать имя сочетания клавиш. Дополнительные сведения о пунктах меню и сочетаний клавиш см. в разделе [связывание пункта меню с сочетанием клавиш](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сочетаний клавиш](../windows/accelerator-editor.md)  
[Редакторы ресурсов](../windows/resource-editors.md)
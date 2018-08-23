---
title: Задание свойств сочетаний клавиш | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d47dffb782da1094c157a7bbd21c40ab6ba9fef
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606708"
---
# <a name="setting-accelerator-properties"></a>Задание свойств сочетаний клавиш

Можно задавать свойства сочетаний клавиш [окно "Свойства"](/visualstudio/ide/reference/properties-window) в любое время. Можно также использовать **Accelerator** редактор для изменения свойств сочетаний клавиш в таблице сочетаний клавиш. Изменения, внесенные с помощью **свойства** окна или **Accelerator** редактор имеет тот же результат: изменения немедленно отражаются в таблице сочетаний клавиш.

Существует три свойства для каждого сочетания [идентификатор](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160):

- [Свойство "модификатор"](../windows/accelerator-modifier-property.md) задает комбинации управляющих клавиш для сочетания клавиш.

   > [!NOTE]
   > В **свойства** окно, это свойство появляется как три отдельных логических свойства, все из которых можно управлять независимо друг от друга: **Alt**, **Ctrl**и **Shift**.

- [Ключевое свойство](../windows/accelerator-key-property.md) задает фактический ключ для использования в качестве сочетания клавиш.

- [Свойство типа](../windows/accelerator-type-property.md) определяет, интерпретируется ли ключ как виртуальный (VIRTKEY) или ASCII/ANSI.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Стандартные сочетания клавиш](../windows/predefined-accelerator-keys.md)  
[Редакторы ресурсов](../windows/resource-editors.md)  
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
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
ms.openlocfilehash: b89f409fcf5a856a2207dd8efa655728f57b3fe8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680139"
---
# <a name="setting-accelerator-properties"></a>Задание свойств сочетаний клавиш

Можно задавать свойства сочетаний клавиш [окно "Свойства"](/visualstudio/ide/reference/properties-window) в любое время. Можно также использовать **Accelerator** редактор для изменения свойств сочетаний клавиш в таблице сочетаний клавиш. Изменения, внесенные с помощью **свойства** окна или **Accelerator** редактор имеет тот же результат: изменения немедленно отражаются в таблице сочетаний клавиш.

Существует три свойства для каждого идентификатор ускорителя:

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
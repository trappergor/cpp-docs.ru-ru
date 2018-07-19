---
title: Задание свойств сочетаний клавиш | Документы Microsoft
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
ms.openlocfilehash: 5198fc1958863d3b5ad560ffeb8c5576506e9e46
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888850"
---
# <a name="setting-accelerator-properties"></a>Задание свойств сочетаний клавиш
Можно задать свойства сочетаний клавиш в [окно свойств](/visualstudio/ide/reference/properties-window) в любое время. Можно также использовать редактор сочетаний клавиш для изменения свойств сочетаний клавиш в таблице сочетаний клавиш. Изменения, внесенные с помощью окна свойств или редактора сочетаний клавиш, имеют один и тот же результат: изменения немедленно отражаются в таблице сочетаний клавиш.  
  
 Существует три свойства для каждого сочетания [идентификатор](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   [Свойство "модификатор"](../windows/accelerator-modifier-property.md) задает комбинации управляющих клавиш для сочетания клавиш.  
  
    > [!NOTE]
    >  В окне свойств это свойство появляется как три отдельных логических свойства, каждым из которых можно управлять независимо: Alt, Ctrl или Shift.  
  
-   [Ключевое свойство](../windows/accelerator-key-property.md) задает фактический ключ для использования в качестве сочетания клавиш.  
  
-   [Свойство типа](../windows/accelerator-type-property.md) определяет, интерпретируется ли ключ как виртуальный (VIRTKEY) или ASCII/ANSI.  
  

  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Стандартные сочетания клавиш](../windows/predefined-accelerator-keys.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
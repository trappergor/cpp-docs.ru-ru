---
title: Свойство "модификатор" сочетания | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d99d4656f2835f9adb60f310e429c4ccb97ac7b6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="accelerator-modifier-property"></a>Свойство "Модификатор" сочетания клавиш
Ниже приведены допустимые значения для свойства "модификатор" в таблице сочетаний клавиш.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**None**|Пользователь нажимает только значения ключа. Наиболее эффективно используется со значениями ASCII/ANSI 001 до 026, которые интерпретируются как ^ A – ^ Z (CTRL + A до CTRL-Z).|  
|**ALT**|Пользователь должен клавишу ALT перед значением ключа.|  
|**CTRL**|Пользователь должен клавишу CTRL перед значением ключа. Не является допустимым типа ASCII.|  
|**SHIFT**|Пользователь должен клавишу SHIFT перед значением ключа.|  
|**Ctrl + Alt**|Пользователь должен нажать клавишу CTRL и ALT, прежде чем значения ключа. Не является допустимым типа ASCII.|  
|**Ctrl + Shift**|Пользователь должен нажать клавишу CTRL и SHIFT, прежде чем значения ключа. Не является допустимым типа ASCII.|  
|**Alt + Shift**|Пользователь должен нажать клавишу ALT и клавишу SHIFT, прежде чем значения ключа. Не является допустимым типа ASCII.|  
|**Ctrl + Alt + Shift**|Пользователь должен нажать клавишу CTRL, SHIFT и ALT перед значением ключа. Не является допустимым типа ASCII.|  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Задание свойств сочетаний клавиш](../windows/setting-accelerator-properties.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
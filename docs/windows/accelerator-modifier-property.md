---
title: "Свойство \"модификатор\" сочетания | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d54c131af740c9c2248c4d923176b0a5c55d9e33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
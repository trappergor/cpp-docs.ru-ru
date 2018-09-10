---
title: Свойство "модификатор" сочетания (C++) | Документация Майкрософт
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
ms.openlocfilehash: 793e02b4ac083d6fe84ba2cc76ee340bcf2484e9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316059"
---
# <a name="accelerator-modifier-property-c"></a>Свойство "модификатор" сочетания (C++)

Ниже приведены допустимые значения для свойства "модификатор" в таблице сочетаний клавиш.

|Значение|Описание|
|-----------|-----------------|
|**None**|Пользователь нажимает только **ключ** значение. Это наиболее эффективно используется со значениями ASCII/ANSI 001 до 026, которая интерпретируется как ^ A – ^ Z (CTRL-A-CTRL-Z).|
|**ALT**|Пользователь должен нажать **Alt** ключа перед **ключ** значение.|
|**CTRL**|Пользователь должен нажать **Ctrl** ключа перед **ключ** значение. Не является допустимым с типом ASCII.|
|**SHIFT**|Пользователь должен нажать **Shift** ключа перед **ключ** значение.|
|**Ctrl + Alt**|Пользователь должен нажать **Ctrl** ключ и **Alt** ключа перед **ключ** значение. Не является допустимым с типом ASCII.|
|**Ctrl + Shift**|Пользователь должен нажать **Ctrl** ключ и **Shift** ключа перед **ключ** значение. Не является допустимым с типом ASCII.|
|**Alt + Shift**|Пользователь должен нажать **Alt** ключ и **Shift** ключа перед **ключ** значение. Не является допустимым с типом ASCII.|
|**Ctrl + Alt + Shift**|Пользователь должен нажать **Ctrl**, **Alt**, и **Shift** перед **ключ** значение. Не является допустимым с типом ASCII.|

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Задание свойств сочетаний клавиш](../windows/setting-accelerator-properties.md)  
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
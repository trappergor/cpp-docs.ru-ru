---
title: Свойство "модификатор" сочетаний клавиш | Документация Майкрософт
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
ms.openlocfilehash: 7e6750bfc0195eaaa350b829d1d899f648e9fe0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592640"
---
# <a name="accelerator-modifier-property"></a>Свойство "Модификатор" сочетания клавиш

Ниже приведены допустимые значения для свойства "модификатор" в таблице сочетаний клавиш.

|Значение|Описание:|
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
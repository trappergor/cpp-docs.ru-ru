---
title: Добавление записи в таблицу сочетаний клавиш (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7055c21a2b9e7d0e32f3dac56641513b19953e18
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315585"
---
# <a name="adding-an-entry-to-an-accelerator-table-c"></a>Добавление записи в таблицу сочетаний клавиш (C++)

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Добавление записи в таблицу сочетаний клавиш

1. В проект C++, откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Щелкните правой кнопкой мыши внутри таблицы сочетаний клавиш и выберите **новый акселератор** из контекстного меню или щелкните пустую строку в нижней части таблицы.

3. Выберите [идентификатор](id-property.md) из раскрывающегося списка в Идентификаторе поле или введите новый идентификатор в **идентификатор** поле.

4. Тип [ключ](../windows/accelerator-key-property.md) вы хотите использовать в качестве сочетаний клавиш или щелкните правой кнопкой мыши и выберите **сочетания клавиш** в контекстном меню, чтобы задать сочетание клавиш ( **сочетания клавиш** команда также доступно в центре **изменить** меню).

5. Изменение [модификатор](../windows/accelerator-modifier-property.md) и [типа](../windows/accelerator-type-property.md)и при необходимости.

6. Нажмите клавишу **ВВОД**.

   > [!NOTE]
   > Убедитесь в том, что все определяемые сочетания клавиш уникальны. У вас есть несколько сочетаний клавиш, назначенных с не оказывает никакого эффекта, например, один и тот же идентификатор **Ctrl** + **P** и **F8** могут быть назначены для ID_PRINT. Тем не менее, при необходимости сочетание клавиш назначено более чем одному идентификатор не будет работать правильно, например, **Ctrl** + **Z** назначить ID_SPELL_CHECK и ID_THESAURUS.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактирование в таблицах сочетаний клавиш](../windows/editing-accelerator-tables.md)  
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
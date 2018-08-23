---
title: Удаление записи из таблицы сочетаний клавиш | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
ms.assetid: cc9cd499-dc04-4fe6-9393-a3e471e115a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c191a2e37e4fe99c12486270c34a558cf4e8455
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605411"
---
# <a name="deleting-an-entry-from-an-accelerator-table"></a>Удаление записи из таблицы сочетаний клавиш

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>Удаление записи из таблицы сочетаний клавиш

1. Откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите запись, которую требуется удалить. (Удерживайте **Ctrl** или **Shift** ключа во время щелчка, чтобы выбрать несколько записей.)

3. Щелкните правой кнопкой мыши и выберите **удалить** в контекстном меню (или выберите **удалить** из **изменить** меню).

\- или -

- Нажмите клавишу **удалить** ключ.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактирование в таблицах сочетаний клавиш](../windows/editing-accelerator-tables.md)  
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
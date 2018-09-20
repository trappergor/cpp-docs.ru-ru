---
title: Редактирование в таблице сочетаний клавиш (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 57347b88fe7d54813e06cde6d5f4b3414e79f116
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395814"
---
# <a name="editing-in-an-accelerator-table-c"></a>Редактирование в таблице сочетаний клавиш (C++)

### <a name="to-edit-in-an-accelerator-table"></a>Редактирование в таблице сочетаний клавиш

1. Откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите запись в таблице и щелкните ее для активации режима редактирования "на месте".

3. Выберите значение из раскрывающегося списка или введите вручную нужное изменение.

   - Для [идентификатор](id-property.md), выберите из списка или введите новое.

   - Для [модификатор](../windows/accelerator-modifier-property.md), выберите из списка.

   - Для [ключ](../windows/accelerator-key-property.md), выберите из списка или введите новое.

   - Для [тип](../windows/accelerator-type-property.md)выберите **ASCII** или **VIRTKEY** из списка.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактирование в таблицах сочетаний клавиш](../windows/editing-accelerator-tables.md)<br/>
[Редактор сочетаний клавиш](../windows/accelerator-editor.md)
---
title: Редактирование в таблице сочетаний клавиш | Документы Microsoft
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
ms.openlocfilehash: 5defa8cdd2e2fb96ceff0d333f06698154baf977
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871732"
---
# <a name="editing-in-an-accelerator-table"></a>Редактирование в таблице сочетаний клавиш
### <a name="to-edit-in-an-accelerator-table"></a>Редактирование в таблице сочетаний клавиш  
  
1.  Откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Выберите запись в таблице и щелкните ее для активации режима редактирования "на месте".  
  
3.  Выберите значение из раскрывающегося списка или введите вручную нужное изменение.  
  
    -   Для [идентификатор](id-property.md), выберите из списка или введите новое.  
  
    -   Для [модификатор](../windows/accelerator-modifier-property.md), выберите из списка.  
  
    -   Для [ключ](../windows/accelerator-key-property.md), выберите из списка или введите новое.  
  
    -   Для [тип](../windows/accelerator-type-property.md), выберите из списка ASCII или VIRTKEY.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.*  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактирование таблиц сочетаний клавиш](../windows/editing-accelerator-tables.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
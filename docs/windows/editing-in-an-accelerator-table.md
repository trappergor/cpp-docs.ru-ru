---
title: "Редактирование в таблице сочетаний клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 756c42999edbf859fac0e5008f55f212883f1822
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактирование таблиц сочетаний клавиш](../windows/editing-accelerator-tables.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
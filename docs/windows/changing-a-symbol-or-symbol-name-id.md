---
title: "Изменение символа или символьного имени (идентификатор) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.symbol.changing
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0ed56fc3663b99af311c52e463bd2f16fcef0a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Изменение символа или символьного имени (идентификатор)
При создании нового ресурса или объекта ресурса среда разработки присваивает ему имя символа, заданное по умолчанию, например, IDD_DIALOG1. Можно использовать [окно свойств](/visualstudio/ide/reference/properties-window) изменить имя символа по умолчанию или изменить имя любого символа, уже связанного с ресурсом.  
  
### <a name="to-change-a-resources-symbol-name"></a>Изменение имени символа ресурса  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), выберите ресурс.  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В **свойства** введите новое имя символа или выберите из списка существующих символов в **идентификатор** поле.  
  
     При вводе нового имени символа ему автоматически присваивается значение.  
  
 Можно использовать [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md) изменять имена символов, в данный момент не назначенных ресурсу. Дополнительные сведения см. в разделе [изменение неназначенных символов](../windows/changing-unassigned-symbols.md).  
  

  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Ограничения для имен символов](../windows/symbol-name-restrictions.md)   
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)
---
title: "Свойство типа сочетаний клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ef1788f451597cdc8d3b512f5eede3c3d5abb382
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="accelerator-type-property"></a>Свойство "Тип" сочетания клавиш
Сочетания клавиш **тип** свойство определяет, является ли сочетание клавиш, связанное с Идентификатором ускорителя виртуальным сочетанием клавиш или значением ключа ASCII/ANSI:  
  
-   Если **тип** свойство **ASCII**, [модификатор](../windows/accelerator-modifier-property.md) может быть только один или Alt, или он может иметь сочетание клавишу CTRL (определяемое перед клавишей ^).  
  
-   Если **тип** свойство **VIRTKEY**, допустимо любое сочетание модификатора и значений клавиш.  
  
    > [!NOTE]
    >  Если вы хотите ввести значение в таблице сочетаний клавиш и имеют значение рассматриваться как ASCII/ANSI, просто щелкните тип записи в таблице и выберите "ASCII" из раскрывающегося списка. Тем не менее при использовании **сочетания клавиш** команда (**изменить** меню) для указания ключа, необходимо изменить **тип** значение ASCII от VIRTKEY *перед* вводить код клавиши.  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Задание свойств сочетаний клавиш](../windows/setting-accelerator-properties.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
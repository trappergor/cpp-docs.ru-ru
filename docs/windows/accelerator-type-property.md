---
title: Свойство типа сочетаний клавиш | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cb1ba8f117fadab7cccb835ba8889d57bcc9f184
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856505"
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
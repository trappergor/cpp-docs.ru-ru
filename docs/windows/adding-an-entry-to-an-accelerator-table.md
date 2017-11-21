---
title: "Добавление записи в таблице сочетаний клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fcfc3198393d052910d7e180e4f8d2725b15ad88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>Добавление записи в таблицу сочетаний клавиш
### <a name="to-add-an-entry-to-an-accelerator-table"></a>Добавление записи в таблицу сочетаний клавиш  
  
1.  Откройте таблицу сочетаний клавиш, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Щелкните правой кнопкой мыши внутри таблицы сочетаний клавиш и выберите **создать сочетание клавиш** из контекстного меню или щелкните пустую строку в нижней части таблицы.  
  
3.  Выберите [идентификатор](id-property.md) из раскрывающегося списка в Идентификаторе или введите новый идентификатор в **идентификатор** поле.  
  
4.  Тип [ключ](../windows/accelerator-key-property.md) вы хотите использовать в виде сочетаний клавиш или щелкните правой кнопкой мыши и выберите **сочетания клавиш** из контекстного меню, чтобы задать сочетание клавиш ( **сочетания клавиш** команда также доступны из **изменить** меню).  
  
5.  Изменение [модификатор](../windows/accelerator-modifier-property.md) и [тип](../windows/accelerator-type-property.md)при необходимости.  
  
6.  Нажмите клавишу **ВВОД**.  
  
    > [!NOTE]
    >  Убедитесь в том, что все определяемые сочетания клавиш уникальны. Одному и тому же идентификатору можно назначить несколько разных сочетаний клавиш, например, CTRL + P и F8 назначить ID_PRINT. Это не приведет к ошибкам. Однако назначение одного и того же сочетания клавиш нескольким идентификаторам приведет к неправильной работе, например, если CTRL + Z назначить ID_SPELL_CHECK и ID_THESAURUS.  
  

  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактирование таблиц сочетаний клавиш](../windows/editing-accelerator-tables.md)   
 [Редактор сочетаний клавиш](../windows/accelerator-editor.md)
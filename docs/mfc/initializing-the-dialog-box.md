---
title: "Инициализация диалогового окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6568c9bd9002df880a5501dd68e7050a4dc14706
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="initializing-the-dialog-box"></a>Инициализация диалогового окна
После диалогового окна поле и всех ее элементов управления создаются, но перед диалогового окна поле (любого типа) отображается на экране, объекта диалогового окна [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) вызвать функцию-член. Для модального диалогового окна, это происходит во время `DoModal` вызова. Для немодального диалогового окна `OnInitDialog` вызывается, когда **создать** вызывается. Обычно переопределяется `OnInitDialog` для инициализации диалогового элементы управления, например установку исходный текст из поля редактирования. Необходимо вызвать `OnInitDialog` функции-члена базового класса, `CDialog`, из вашей `OnInitDialog` переопределения.  
  
 Если вы хотите установить цвет фона диалогового окна (и, все другие диалоговые окна в приложении), см. раздел [Установка цвета фона диалогового](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)


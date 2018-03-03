---
title: "Как: обновление объектов пользовательского интерфейса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91e6d13e840c29d3ea9600183fafd9260966a2f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-update-user-interface-objects"></a>Практическое руководство. Обновление объектов интерфейса пользователя
Как правило пункты меню и кнопки панели инструментов имеет более одного состояния. Например элемент меню отображается серым цветом (серым цветом), если она недоступна в контексте присутствует. Пункты меню также может быть помечен или нет. Кнопки панели инструментов также может быть отключена, если эта кнопка недоступна, или может быть проверено.  
  
 Кто обновляет состояние для этих элементов, как программировать изменение условий логически, если элемент меню создает команду, которая обрабатывается, например, документ, имеет смысл провести обновление меню элемента документа. Возможно, документ содержит сведения, на котором основан обновления.  
  
 Если команда имеет несколько объектов пользовательского интерфейса (возможно пункта меню и кнопки панели инструментов), оба направляются в той же функции обработчика. Это инкапсулирует код обновления пользовательского интерфейса для всех объектов эквивалентные пользовательского интерфейса в одном месте.  
  
 Платформа предоставляет удобный интерфейс для автоматического обновления объектов пользовательского интерфейса. Вы можете выполнить обновление иным способом, но интерфейс, предоставленный эффективный и простые в использовании.  
  
 В следующих разделах описано использование обработчиков обновления:  
  
-   [Ситуации вызова обработчиков обновления](../mfc/when-update-handlers-are-called.md)  
  
-   [ON_UPDATE_COMMAND_UI-макрос](../mfc/on-update-command-ui-macro.md)  
  
-   [CCmdUI-класс](../mfc/the-ccmdui-class.md)  
  
## <a name="see-also"></a>См. также  
 [Меню](../mfc/menus-mfc.md)


---
title: "Диалоговые окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e4417fc2d4714a249b04bb0c1d04e5642495835
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-boxes"></a>Диалоговые окна
Приложения для Windows часто взаимодействия с пользователем по диалоговым окнам. Класс [CDialog](../mfc/reference/cdialog-class.md) предоставляет интерфейс для управления диалоговым окнам, редактор диалоговых окон Visual C++ позволяет легко спроектировать диалоговые окна и создать их ресурсов шаблона диалогового окна и мастеры кода упрощают процесс инициализации и Проверка элементов управления в диалоговом окне и по сбору значений, введенных пользователем.  
  
 Диалоговые окна содержат элементы управления, включая:  
  
-   Общие элементы управления Windows такие как изменение полей, кнопок, списки, поля со списком, элементов управления древовидного типа список-элементы управления и индикаторы выполнения.  
  
-   Элементы управления ActiveX.  
  
-   Определяемые владельцем элементы управления: элементы управления, которые вы несете ответственность за рисование в диалоговом окне.  
  
 Большинство диалоговых модальное, который пользователю необходимо закрыть диалоговое окно, прежде чем использовать любой другой части программы. Однако можно создать немодальные диалоговые окна, которые позволяют пользователям работать с другими окнами при открытом диалоговом окне. MFC поддерживает оба вида диалоговое окно с классом `CDialog`. Элементы управления упорядочиваются и управляются с помощью ресурса шаблона диалогового окна, созданных с помощью [редактор диалоговых окон](../windows/dialog-editor.md).  
  
 [Страницы свойств](../mfc/property-sheets-mfc.md), также известные как диалоговые окна, являются диалоговым окнам, которые содержат «страницы» различных диалоговых элементов управления. Каждая страница имеет «вкладки» в верхней папке. Щелкните вкладку помещает эту страницу в начало диалогового окна.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Пример. Отображение диалогового окна через команду меню](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [Компоненты диалоговых окон в платформе](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [Модальные и немодальные диалоговые окна](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [Вкладки свойств и страницы свойств](../mfc/property-sheets-and-property-pages-mfc.md) в диалоговом окне  
  
-   [Создание ресурса диалогового окна](../mfc/creating-the-dialog-resource.md)  
  
-   [Создание класса диалогового окна с помощью мастеров кода](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [Обмен данными (диалоговых окон DDX) и проверки (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Типобезопасный доступ к элементам управления в диалоговое окно](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Сопоставление сообщений Windows с классом](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [Часто переопределяемые функции-члены](../mfc/commonly-overridden-member-functions.md)  
  
-   [Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)  
  
-   [Классы общих диалоговых окон](../mfc/common-dialog-classes.md)  
  
-   [Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)  
  
-   Создание приложения, пользовательский интерфейс которого является диалоговым окном: в разделе [CMNCTRL1](../visual-cpp-samples.md) или [CMNCTRL2](../visual-cpp-samples.md) образец программ. Мастер приложений предоставляет этот параметр также.  
  
-   [Примеры](../mfc/dialog-sample-list.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)

---
title: 'Элементы управления MFC ActiveX: Свойства | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9d9e4f5e7d777bd147ce36e970e7a30fd875b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-properties"></a>Элементы управления ActiveX в MFC. Свойства
Элемент управления ActiveX запускает события для взаимодействия со своим контейнером элемента управления. Контейнер, в ответ используются методы и свойства для взаимодействия с элементом управления. Методы и свойства похожи и назначение, соответственно, для функций-членов и переменных-членов класса C++. Свойства являются элементами данных элемента управления ActiveX, предоставляемых для любого контейнера. Свойства предоставляют интерфейс для приложений, содержащих элементы управления ActiveX, таких как клиенты автоматизации и контейнеры элементов управления ActiveX.  
  
 Свойства также называются атрибуты.  
  
 Дополнительные сведения о методах элемента управления ActiveX см. в статье [элементы управления MFC ActiveX: методы](../mfc/mfc-activex-controls-methods.md).  
  
 Элементы управления ActiveX можно реализовать, биржевая и пользовательские методы и свойства. Класс `COleControl` предоставляет реализацию для стандартных свойств. (Полный список стандартных свойств, см. в статье [элементы управления MFC ActiveX: Добавление свойств Stock](../mfc/mfc-activex-controls-adding-stock-properties.md).) Пользовательские свойства, определяемые разработчиком, добавьте специальные возможности для элемента управления ActiveX. Дополнительные сведения см. в разделе [элементы управления MFC ActiveX: Добавление настраиваемых свойств](../mfc/mfc-activex-controls-adding-custom-properties.md).  
  
 Пользовательские и стандартных свойств, как и методы, поддерживаются при помощи механизма, состоящая из подготовки к отправке карта, которая обрабатывает свойств и методов существующих функций-членов `COleControl` класса. Кроме того эти свойства могут иметь параметры, которые разработчик использует для передачи дополнительных сведений в элемент управления.  
  
 Следующие статьи рассматриваются свойства элемента управления ActiveX, более подробно:  
  
-   [Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Элементы ActiveX в MFC. Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Элементы ActiveX в MFC. Реализация расширенных свойств](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [Элементы ActiveX в MFC. Доступ к внешним свойствам](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)


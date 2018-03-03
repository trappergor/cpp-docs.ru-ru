---
title: "Элементы управления MFC ActiveX: Свойства | Документы Microsoft"
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
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eea42401255f0aa99dd7a42b8e9b69e45dfe7b5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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


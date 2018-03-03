---
title: "Элементы управления MFC ActiveX: Методы | Документы Microsoft"
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
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e3b343b13118930612e4adfed4c33a65a9e7be8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-methods"></a>Элементы управления ActiveX в MFC. Методы
Элемент управления ActiveX запускает события для связи между ним и его контейнера элемента управления. Контейнер может также обмениваться данными с элементом управления с помощью методов и свойств. Метода также вызываются функции.  
  
 Методы и свойства обеспечивают интерфейс экспортированный для использования другими приложениями, таких как клиенты автоматизации и контейнеры элементов управления ActiveX. Дополнительные сведения о свойствах элемента управления ActiveX, см. в статье [элементы управления MFC ActiveX: свойства](../mfc/mfc-activex-controls-properties.md).  
  
 Методы аналогичны назначение и функции-члены класса C++. Существует два типа методов, элемент управления можно реализовать: стандартных и пользовательских. Аналогично stock события, stock методы — это методы, для которого [COleControl](../mfc/reference/colecontrol-class.md) обеспечивает реализацию. Дополнительные сведения о стандартных методов см. в статье [элементы управления MFC ActiveX: Добавление методов Stock](../mfc/mfc-activex-controls-adding-stock-methods.md). Настраиваемые методы, определяемые разработчиком, разрешить дополнительные настройки элемента управления. Дополнительные сведения см. в статье [элементы управления MFC ActiveX: Добавление настраиваемых методов](../mfc/mfc-activex-controls-adding-custom-methods.md).  
  
 Библиотека классов Microsoft Foundation (MFC) реализует механизм, позволяющий элементу управления для поддержки биржевая и пользовательских методов. Первая часть — класс `COleControl`. Производное от `CWnd`, `COleControl` стандартных методов, которые являются общими для всех элементов управления ActiveX поддерживают функции-члены. Во второй части этого механизма — карта распределения. Карта распределения похож на схему сообщений; Тем не менее вместо сопоставление функции идентификатор сообщения Windows, карту диспетчеризации сопоставляет виртуальных функций-членов ИДЕНТИФИКАТОРЫ IDispatch.  
  
 Для элемента управления для поддержки различных методов должным образом его класс необходимо объявить карту диспетчеризации. Это достигается с помощью следующей строки кода, расположенный в заголовок класса элемента управления (. H) файла.  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]  
  
 Карта распределения главной предназначена для установления отношений между имена методов, используемых внешняя вызывающая сторона (например, контейнер) и функции-члены класса элемента управления, реализующих методы. После объявления карты распределения он должен быть определен в реализации элемента управления (. Файл CPP). Следующие строки кода определяют схему распределения:  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]  
  
 Если вы использовали [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md) для создания проекта, эти строки были добавлены автоматически. Если не использовался мастер элементов управления ActiveX MFC, необходимо добавить эти строки вручную.  
  
 Следующие статьи рассматриваются методы подробно:  
  
-   [Элементы ActiveX в MFC. Добавление стандартных методов](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Элементы ActiveX в MFC. Добавление пользовательских методов](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Элементы ActiveX в MFC. Возврат кодов ошибок из метода](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)


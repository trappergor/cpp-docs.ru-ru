---
title: "Как: Создание виртуальной схемы сообщений для класса шаблона | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e593d1b75265a1c58c82278920bda92ddf58929
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона
Сопоставление сообщений в MFC предоставляет эффективный способ направлять сообщения Windows к соответствующему экземпляру объекта C++. Целевые объекты карты сообщений MFC примеры классов приложения, документ и представление классов, классы элементов управления и т. д.  
  
 Традиционные схемы сообщений MFC объявляются с помощью [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) макрос для объявления начала схему сообщений, запись макроса для каждого метода класса обработчика сообщений и, наконец, [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)макрос для объявления конец схему сообщений.  
  
 Единственным ограничением с [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) макрос происходит, когда он используется в сочетании с классом, содержащий аргументы шаблона. При использовании с классом шаблона, этот макрос приведет к ошибке компиляции из-за отсутствующих параметров шаблона в расширении макроса. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) макрос было разработано для помощи сопоставляет классы, содержащие аргументом один шаблон для объявления свои собственные сообщения.  
  
## <a name="example"></a>Пример  
 Рассмотрим пример, где MFC [CListBox](../mfc/reference/clistbox-class.md) класс расширен для обеспечения синхронизации с внешним источником данных. Вымышленный **CSyncListBox** класс объявляется следующим образом:  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 **CSyncListBox** класс является шаблоном для одного типа, описывающий источник данных, он будет синхронизироваться с. Он также объявляет три метода, которые будут участвовать в схеме сообщений класса: **OnPaint**, **OnDestroy**, и **OnSynchronize**. **OnSynchronize** метод реализуется следующим образом:  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 Реализация выше позволяет **CSyncListBox** класс специализированным на любой тип класса, который реализует **GetCount** метода, такие как **CArray**, **CList**, и **CMap**. **StringizeElement** функция — это функция шаблона, созданным с помощью следующего:  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 Как правило сопоставление сообщений для этого класса будут определены как:  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 где **LBN_SYNCHRONIZE** пользовательский сообщение, определенный приложением, такие как:  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 Выше карты макроса не будет компилироваться, из-за того, что спецификация шаблона для **CSyncListBox** класса будут отсутствовать во время расширения макроса. **BEGIN_TEMPLATE_MESSAGE_MAP** макрос устраняет эту проблему путем включения параметра указанного шаблона в сопоставление расширенному макросу. Сопоставление сообщений для этого класса выглядит следующим образом:  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 Следующий код демонстрирует пример использования оператора **CSyncListBox** класса с помощью **CStringList** объекта:  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 Для завершения проверки, **StringizeElement** функцию, специализированную для работы с **CStringList** класса:  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)


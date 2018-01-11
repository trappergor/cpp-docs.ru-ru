---
title: "Функции записи просмотра классов (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c975aac0459a13a3fb95fdec3dff1a648b0efec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Функциональные возможности классов представления записей (доступ к данным MFC)
Можно сделать программированием доступа к данным на основе форм с классом [CFormView](../mfc/reference/cformview-class.md), но [CRecordView](../mfc/reference/crecordview-class.md) обычно является более класс для наследования. В дополнение к его `CFormView` функций, `CRecordView`:  
  
-   Обеспечивает обмен данными (диалоговых окон DDX) между элементами управления формы и ассоциированным объектом.  
  
-   Обрабатывает команды Переместить первый, переместить следующий, переместить предыдущий и переместить последний для перемещения по записям в связанном объекте набора записей.  
  
-   Сохраняет изменения в текущей записи при переходе к другой записи.  
  
 Дополнительные сведения о навигации, см. в разделе [представления записей: поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>См. также  
 [Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
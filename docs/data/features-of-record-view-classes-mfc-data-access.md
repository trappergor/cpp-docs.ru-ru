---
title: Функции записи просмотра классов (доступ к данным MFC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b1c99b8b271b4948584d9bdb25c74518fe835573
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093224"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Функциональные возможности классов представления записей (доступ к данным MFC)

Можно сделать программирование доступа к данным на основе форм с использованием класса [CFormView](../mfc/reference/cformview-class.md), но [CRecordView](../mfc/reference/crecordview-class.md) обычно является лучшим класса для наследования. В дополнение к его `CFormView` функций, `CRecordView`:  
  
- Обеспечивает обмен данными диалоговых (окон DDX) между элементами управления формы и ассоциированным объектом набора записей.  
  
- Обрабатывает команды Переместить первый, переместить следующий, переместить предыдущий и переместить последний для перемещения по записям в связанном объекте набора записей.  
  
- Сохраняет изменения текущей записи в том случае, когда пользователь переходит на другую запись.  
  
Дополнительные сведения о навигации, см. в разделе [представления записей: поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>См. также  

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
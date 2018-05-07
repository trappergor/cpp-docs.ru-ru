---
title: Команда обработчики (доступ к данным MFC) перемещения по записям | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03dec2e3eff0f61db5f4c8b7573400a589615b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Обработчики команд для прокрутки записей (доступ к данным MFC) 
[CRecordView](../mfc/reference/crecordview-class.md) класс предоставляет обработку по умолчанию для следующих стандартных команд:  
  
-   **ID_RECORD_MOVE_FIRST**  
  
-   **ID_RECORD_MOVE_LAST**  
  
-   **ID_RECORD_MOVE_NEXT**  
  
-   **ID_RECORD_MOVE_PREV**  
  
 `OnMove` Функция-член предоставляет обработку по умолчанию для всех четырех команд, которые переходят от записи к записи. Если команды даны, RFX (или DFX) загружает новую запись в поля набора записей и DDX передвигает значения в элементы управления формы записи. Сведения об RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Обязательно используйте стандартные идентификаторы команд для любых объектов пользовательского интерфейса, связанных с стандартными командами перехода к записи.  
  
## <a name="see-also"></a>См. также  
 [Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
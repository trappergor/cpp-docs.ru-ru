---
title: Обмен данными в представлениях записей (доступ к данным MFC) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58bda2d9a712e38951b8201c08e5bbbe369537eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Обмен данными в представлениях записей (доступ к данным MFC)
При использовании [добавить класс](../mfc/reference/adding-an-mfc-odbc-consumer.md) для сопоставления элементов управления в ресурс шаблона диалоговых окон для просмотра записи полям набора записей, среда управляет обменом данных в обоих направлениях — из набора данных к элементам управления и элементов управления в набор записей. Использование механизма DDX означает, что нет необходимости писать код передачи данных туда и обратно самостоятельно.  
  
 DDX для представлений записей работает вместе с [RFX](../data/odbc/record-field-exchange-rfx.md) для набора записей класса `CRecordset` (ODBC).  RFX перемещает данные между текущей записью источника данных и элементами данных полей объекта набора записей. DDX перемещает данные из элементов данных полей в элементы управления в форме. Данная комбинация заполняет элементы управления формы в начале и по мере того как пользователь перемещается от записи к записи. Также может перемещать обновленные данные обратно в набор записей, а затем в источник данных.  
  
 На следующем рисунке показана связь между DDX и RFX для представлений записей.  
  
 ![Диалоговое окно&#45;обмена данными и записи&#45;поле exchange](../data/media/vc37xt1.gif "vc37xt1")  
Обмен данными в диалоговом окне и обмен полями записи  
  
 Дополнительные сведения об DDX см. в разделе [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md). Дополнительные сведения об RFX см. в разделе [обмен полей записей (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>См. также  
 [Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
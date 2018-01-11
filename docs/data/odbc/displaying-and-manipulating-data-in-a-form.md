---
title: "Отображение и обработка данных в форме | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a7960780f1f83833e25c9a094a36314a299a042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>Отображение и обработка данных в форме
Многие приложения доступа к данным выберите данные и отобразить их в поля в форме. Класс database [CRecordView](../../mfc/reference/crecordview-class.md) дает [CFormView](../../mfc/reference/cformview-class.md) объекта непосредственно соединен с объектом набора записей. Представление записей использует [обмен данными (диалоговых окон DDX)](../../mfc/dialog-data-exchange-and-validation.md) для перемещения значения полей текущей записи из набора записей в элементы управления на форме и возврата обновленных данных в набор записей. Набор записей, в свою очередь, использует обмен полями записей (RFX) для перемещения данных между его члены данных полей и соответствующими столбцами в таблице в источнике данных.  
  
 Можно использовать мастера приложений MFC или **добавить класс** (как описано в [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для создания класса представления и его связанного набора записей класса совместно.  
  
 Представления записей и его набор записей, удаляются при закрытии документа. Дополнительные сведения о представлениях записей см. в разделе [представления записей](../../data/record-views-mfc-data-access.md). Дополнительные сведения об RFX см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>См. также  
 [ODBC и MFC](../../data/odbc/odbc-and-mfc.md)
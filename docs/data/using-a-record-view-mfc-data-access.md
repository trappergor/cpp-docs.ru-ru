---
title: Использование представления записей (доступ к данным MFC) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23dd3335f6c77a3efec26f13e78824806f05821a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104647"
---
# <a name="using-a-record-view--mfc-data-access"></a>Использование представления записей (доступ к данным MFC)
В этом разделе объясняется, как настроить код по умолчанию для представлений записей, создаваемых мастером для вас. Как правило, требуется ограничить выбор записей с [фильтра](../data/odbc/recordset-filtering-records-odbc.md) или [параметры](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), возможно [сортировки](../data/odbc/recordset-sorting-records-odbc.md) записи, настроить инструкцию SQL.  
  
 С помощью `CRecordView` является так же, как с помощью [CFormView](../mfc/reference/cformview-class.md). Основной подход заключается в использовании представления записей для отображения и возможно, обновления записей одного определенного набора записей. Кроме этого, может возникнуть необходимость использования других наборов записей, как описано в [представления записей: заполнение списка из второго набора записей](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## <a name="see-also"></a>См. также  
 [Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)   
 [Список драйверов ODBC](../data/odbc/odbc-driver-list.md)
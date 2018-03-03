---
title: "Перетаскивание: Настройка | Документы Microsoft"
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
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 387344160cf2009b19ad8de820eabc6063ae1f7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-customizing"></a>Перетаскивание. Настройка
Реализация по умолчанию и перетащите функции достаточно для большинства приложений. Для некоторых приложений может потребоваться изменить это стандартное поведение. В этой статье описаны шаги, необходимо изменить эти значения по умолчанию. Кроме того этот метод можно использовать для установки приложения, которые не поддерживают составных документов в качестве источников перетаскивания.  
  
 Если вы настраиваете стандартное поведение OLE и перетащите или приложение, отличных от OLE, необходимо создать `COleDataSource` объект, содержащий данные. Когда пользователь начинает операцию перетаскивания и вставки, код должен вызывать `DoDragDrop` функции из этого объекта, а не от других классов, поддерживающие операции перетаскивания и вставки.  
  
 При необходимости можно создать `COleDropSource` объект для управления раскрывающегося и переопределить некоторые из функций в зависимости от типа поведения, чтобы изменить его. Этот объект источника перетаскивания затем передается `COleDataSource::DoDragDrop` для изменения поведения по умолчанию для этих функций. Эти разные параметры позволяют большую гибкость в поддержке операции перетаскивания и вставки в приложении. Дополнительные сведения об источниках данных см. в статье [объектов данных и источники данных (OLE)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Можно переопределить для настройки операций перетаскивания и вставки следующие функции:  
  
|Переопределение|Для настройки|  
|--------------|------------------|  
|`OnBeginDrag`|Как перетаскивание инициируется после вызова метода `DoDragDrop`.|  
|`GiveFeedback`|Визуальную обратную связь, такие как внешний вид курсора для различных результатов.|  
|`QueryContinueDrag`|Завершение операции перетаскивания и вставки. Эта функция позволяет проверять модификатор ключевых состояний во время операции перетаскивания.|  
  
## <a name="see-also"></a>См. также  
 [Перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)   
 [Класс COleDropSource](../mfc/reference/coledropsource-class.md)   
 [Класс COleDataSource](../mfc/reference/coledatasource-class.md)

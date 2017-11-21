---
title: "Использование представлений записей OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4e57f320c8b207e7b1c8721ab25744cd1f128bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-ole-db-record-views"></a>Использование представлений записей OLE DB
Если требуется отобразить данные набора строк OLE DB в приложении MFC, следует использовать класс MFC [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Объект представления записей создан из `COleDBRecordView` позволяет отображать записи базы данных в элементах управления MFC. Представление записей — представление формы диалогового окна, непосредственно подключенные к объекту набора строк OLE DB, созданные на основе `CRowset` класса шаблона. Получение дескриптора для объекта набора строк проста:  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 В представлении отображаются поля `CRowset` в элементах управления диалогового окна. `COleDBRecordView` Объект использует Exchange данных диалогового окна (DDX) и навигационные функции встроены в `CRowset` (**MoveFirst**, `MoveNext`, `MovePrev`, и `MoveLast`) для автоматизации перемещения данных между элементами управления в форме и полями набора строк. `COleDBRecordView`хранит список положение пользователя в наборе строк, чтобы представление записей можно обновить пользовательский интерфейс и предоставляет [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) метод для обновления текущей записи перед переходом на другой.  
  
 Можно использовать функции DDX с **COleDbRecordView** для получения данных непосредственно из набора записей базы данных и его отображения в элементе управления диалогового окна. Следует использовать **DDX_\***  методы (такие как `DDX_Text`), а не **DDX_Field\***  функции (такие как `DDX_FieldText`) с **COleDbRecordView** .  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [Класс COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)
---
title: Использование представлений записей OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ba772afc5cd4c1dd1cf6014339c8779bec476b48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058579"
---
# <a name="using-ole-db-record-views"></a>Использование представлений записей OLE DB

Если вы хотите отобразить данные набора строк OLE DB в приложении MFC, следует использовать класс MFC [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Созданный объект представления записей из `COleDBRecordView` позволяет отображать записи базы данных в элементы управления MFC. Представление записей — это представление формы диалогового окна, непосредственно подключенные к объект набора строк OLE DB, созданный из `CRowset` класс шаблона. Получение дескриптора объекта набора строк прост:  
  
```cpp  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
В представлении отображаются поля `CRowset` в элементах управления диалогового окна. `COleDBRecordView` Объект использует Exchange данных диалогового окна (DDX) и навигационные функции встроены в `CRowset` (`MoveFirst`, `MoveNext`, `MovePrev`, и `MoveLast`) для автоматизации перемещения данных между элементами управления на форме и поля для набора строк. `COleDBRecordView` отслеживает этой положение пользователя в наборе строк, представление записей можно обновить пользовательский интерфейс и предоставляет [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) метод для обновления текущей записи перед переходом на другой.  
  
Можно использовать функции DDX с `COleDbRecordView` для получения данных непосредственно из набора записей базы данных и отображения его в элемент управления диалогового окна. Следует использовать **DDX_** <strong>\*</strong> методы (такие как `DDX_Text`), а не **DDX_Field** <strong>\*</strong> функции (такие как `DDX_FieldText`) с `COleDbRecordView`.  
  
## <a name="see-also"></a>См. также  

[Использование методов доступа](../../data/oledb/using-accessors.md)<br/>
[Класс COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)
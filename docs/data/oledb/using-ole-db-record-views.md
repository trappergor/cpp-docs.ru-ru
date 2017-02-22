---
title: "Использование представлений записей OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView - класс, общие сведения"
  - "MFC - библиотека, представления записей"
  - "представления записей OLE DB"
  - "OLE DB, представления записей"
  - "представления записей, объекты представления записей"
  - "наборы строк, представления записей"
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Использование представлений записей OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При необходимости отображать данные набора строк OLE DB в приложении MFC следует использовать класс MFC [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md).  Объект представления записей, созданный из класса `COleDBRecordView`, позволяет отображать записи баз данных в элементах управления MFC.  Представление записей является диалоговым представлением формы, напрямую подключенным к объекту набора строк OLE DB, созданному из класса шаблонов `CRowset`.  Получить дескриптор для объекта набора строк несложно:  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 В представлении отображаются поля объекта `CRowset` в элементах управления диалогового окна.  Объект `COleDBRecordView` использует набор функций Dialog Data Exchange \(DDX\) и функцию навигации, встроенную в класс `CRowset` \(**MoveFirst**, `MoveNext`, `MovePrev` и `MoveLast`\) для автоматизации перемещения данных между элементами управления формы и полями набора строк.  Представление `COleDBRecordView` отслеживает положение пользователя в наборе строк, чтобы представление записей могло обновлять пользовательский интерфейс, и предоставляет метод [OnMove](../Topic/COleDBRecordView::OnMove.md) для обновления текущей записи перед переходом к следующей.  
  
 Можно использовать функции DDX с представлением **COleDbRecordView** для получения данных непосредственно из набора записей базы данных и отображения их в элементе управления диалогового окна.  С представлением **COleDbRecordView** следует использовать методы **DDX\_\*** \(например, `DDX_Text`\), а не функции **DDX\_Field\*** \(например, `DDX_FieldText`\).  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [COleDBRecordView Class](../../mfc/reference/coledbrecordview-class.md)
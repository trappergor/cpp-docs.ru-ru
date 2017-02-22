---
title: "Использование существующего набора записей ADO | Microsoft Docs"
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
  - "наборы записей ADO [C++]"
  - "шаблоны потребителя OLE DB, наборы записей ADO"
  - "наборы записей [C++], использование в OLE DB"
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Использование существующего набора записей ADO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы смешивать шаблоны объекта\-получателя OLE DB и Active Data Objects \(ADO\), необходимо использовать объекты ADO для открытия набора записей \(соответствующего набору строк в объекте\-получателе шаблонов OLE DB\).  При получении набора записей для подключения к набору записей OLE DB необходимо выполнить следующие действия:  
  
1.  Вызвать `QueryInterface` для указателей `IRowset` и `IAccessor`.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* указывает на объект **IUnknown** набора записей ADO.  
  
2.  Присоединить метод доступа и набор строк к соответствующим классам шаблона объекта\-получателя OLE DB.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)
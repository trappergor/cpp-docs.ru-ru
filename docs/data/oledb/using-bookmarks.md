---
title: "С помощью закладок | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41c8e5a44130eebfddc9e99ab7ef815b6e8e43a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-bookmarks"></a>Использование закладок
Перед открытием набора строк необходимо указать поставщику, что вы хотите использовать закладки. Чтобы сделать это, задайте **DBPROP_BOOKMARKS** свойства **true** в свойство. Поставщик извлекает закладки как нулевой столбец, поэтому необходимо использовать специальный макрос `BOOKMARK_ENTRY` и `CBookmark` класса при использовании статического доступа. `CBookmark`— Это класс шаблона, где аргумент имеет длину в байтах буфера закладки. Длина буфера, необходимая для закладки зависит от поставщика. При использовании поставщика OLE DB для ODBC, как показано в следующем примере размер буфера должен быть 4 байта.  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
  
CTable<CAccessor<CProducts> > product;  
product.Open(session, "Products", &propset);  
```  
  
 Если вы используете `CDynamicAccessor`, буфер выделяется динамически во время выполнения. В этом случае можно использовать специализированную версию `CBookmark` для которого не указывать длину буфера. Используйте функцию `GetBookmark` для получения закладку из текущей записи, как показано в этом примере кода:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 Сведения о поддержке закладок в поставщиках см. в разделе [Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)
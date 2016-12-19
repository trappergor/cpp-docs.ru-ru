---
title: "Использование закладок | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "закладки, OLE DB"
  - "шаблоны поставщика OLE DB, закладки"
  - "поставщики OLE DB, поддержка закладок"
  - "наборы строк, закладки"
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование закладок
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перед открытием набора строк сообщите поставщику про намерение использовать закладки.  Чтобы выполнить это действие, присвойте свойству **DBPROP\_BOOKMARKS** набора свойств значение **true**.  Поставщик извлекает закладки как нулевой столбец, поэтому можно использовать особый макрос `BOOKMARK_ENTRY` и класс `CBookmark`, если используется статический метод доступа.  `CBookmark` является классом шаблона, в котором аргумент является длиной буфера закладок \(в байтах\).  Длина буфера, необходимая для закладки, зависит от типа поставщика.  При использовании поставщика OLE DB ODBC в соответствии со следующим примером, длина буфера должна составлять 4 байта.  
  
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
  
 При использовании `CDynamicAccessor`, буфер динамически выделяется во время выполнения.  В этом случае используется особая версия `CBookmark`, в которой не требуется указывать длину буфера.  Используйте функцию `GetBookmark`, чтобы извлечь закладку из текущей записи, как показано в примере кода:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 Дополнительные сведения о поддержке закладок в поставщиках см. в разделе [Поддержка поставщика для закладок](../../data/oledb/provider-support-for-bookmarks.md).  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)
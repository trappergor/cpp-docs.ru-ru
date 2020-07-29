---
title: Использование закладок
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 8caa33b3bafbaa9e537d9669aa7b60a9355475ef
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218303"
---
# <a name="using-bookmarks"></a>Использование закладок

Перед открытием набора строк необходимо сообщить поставщику, что вы хотите использовать закладки. Для этого задайте `DBPROP_BOOKMARKS` для свойства значение **`true`** в наборе свойств. Поставщик получает закладки в виде нулевого столбца, поэтому при использовании статического метода доступа необходимо использовать специальный макрос BOOKMARK_ENTRY и `CBookmark` класс. `CBookmark`— Это класс шаблона, в котором аргумент представляет собой длину буфера закладки в байтах. Длина буфера, необходимая для закладки, зависит от поставщика. Если вы используете поставщик OLE DB ODBC, как показано в следующем примере, размер буфера должен составлять 4 байта.

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

Затем используется следующий код:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

Если используется `CDynamicAccessor` , буфер динамически задается во время выполнения. В этом случае можно использовать специальную версию, `CBookmark` для которой не указана длина буфера. Используйте функцию, `GetBookmark` чтобы получить закладку из текущей записи, как показано в следующем примере кода:

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

Дополнительные сведения о поддержке закладок в поставщиках см. в разделе [Поддержка закладок поставщиком](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)

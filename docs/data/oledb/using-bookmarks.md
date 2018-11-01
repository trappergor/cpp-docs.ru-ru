---
title: Использование закладок
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 1f8ef4c25ad921dad66e5587f4005585b3e017f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635660"
---
# <a name="using-bookmarks"></a>Использование закладок

Прежде чем открыть набор строк, вы сообщите поставщику, что вы хотите использовать закладки. Чтобы сделать это, установите `DBPROP_BOOKMARKS` свойства **true** в свойство. Поставщик извлекает закладки как нулевой столбец, поэтому необходимо использовать специальный макрос BOOKMARK_ENTRY и `CBookmark` , если вы используете статический метод доступа. `CBookmark` — Это класс шаблона, где аргумент имеет длину в байтах буфера закладки. Длина буфера, необходимая для закладки зависит от поставщика. При использовании поставщика OLE DB для ODBC, как показано в следующем примере, размер буфера должен быть 4 байта.

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

После этого используется следующий код:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

Если вы используете `CDynamicAccessor`, буфер задается динамически во время выполнения. В этом случае можно использовать специальную версию `CBookmark` для которого не указывать длину буфера. Функция `GetBookmark` получить закладки из текущей записи, как показано в этом примере кода:

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

Сведения о поддержке закладок в поставщиках, см. в разделе [Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)
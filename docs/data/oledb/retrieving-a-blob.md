---
title: Извлечение двоичного объекта (BLOB)
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: 352841595e8b197407ccb52a22c8b0502d314c98
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509501"
---
# <a name="retrieving-a-blob"></a>Извлечение двоичного объекта (BLOB)

Большой двоичный объект (BLOB) можно получить различными способами. Можно использовать `DBTYPE_BYTES` для получения большого двоичного объекта в виде последовательности байтов или использовать интерфейс, например `ISequentialStream` . Дополнительные сведения см. в разделе [большие двоичные объекты и OLE](/previous-versions/windows/desktop/ms711511(v=vs.85)) в **справочнике по программисту OLE DB**.

В следующем коде показано, как получить большой двоичный объект с помощью `ISequentialStream` . Макрос [BLOB_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#blob_entry) позволяет указать интерфейс и флаги, используемые для интерфейса. После открытия таблицы код вызывает `Read` многократный вызов `ISequentialStream` для чтения БАЙТОВ из большого двоичного объекта. Код вызывает метод `Release` для удаления указателя интерфейса перед вызовом метода `MoveNext` для получения следующей записи.

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

Затем используется следующий код:

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

categories.Open(session, "Categories");

while (categories.MoveNext() == S_OK)
{
   do
   {
      categories.pPicture->Read(myBuffer, 65536, &cb);
      // Do something with the buffer
   } while (cb > 0);
   categories.pPicture->Release();
}
```

Дополнительные сведения о макросах, обрабатывающих данные больших двоичных объектов, см. в разделе **макросы таблицы Map** в [макросах и глобальных функциях для OLE DB шаблонов потребителей](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)<br/>
[Макросы и глобальные функции для OLE DB шаблонов потребителей](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>

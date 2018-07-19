---
title: Получение большого двоичного ОБЪЕКТА | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 420e863fcd5d4c666bf8e9a25a2f0f53e726c871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105209"
---
# <a name="retrieving-a-blob"></a>Извлечение двоичного объекта (BLOB)
Можно получить большой двоичный объект (BLOB) различными способами. Можно использовать **DBTYPE_BYTES** для получения большого двоичного ОБЪЕКТА как последовательность байтов или используйте интерфейс, как `ISequentialStream`. Дополнительные сведения см. в разделе [большие двоичные ОБЪЕКТЫ и объекты OLE](https://msdn.microsoft.com/en-us/library/ms711511.aspx) в *Справочник программиста OLE DB*.  
  
 Следующий код показывает способ получения больших двоичных ОБЪЕКТОВ с помощью `ISequentialStream`. Макрос [BLOB_ENTRY](../../data/oledb/blob-entry.md) позволяет указать интерфейс и флаги, используемые для этого интерфейса. После открытия таблицы, код вызывает **чтения** несколько раз на `ISequentialStream` для чтения байтов из большого двоичного ОБЪЕКТА. Этот код вызывает **выпуска** для указателя интерфейса до вызова метода dispose `MoveNext` для получения следующей записи.  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories>> categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
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
  
 Дополнительные сведения о макросах, обрабатывающих данные большого двоичного ОБЪЕКТА. в разделе «Макросы столбец схемы» в [макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [Макросы и глобальные функции для шаблонов объектов-получателей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)
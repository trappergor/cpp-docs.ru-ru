---
title: "Извлечение двоичного объекта (BLOB) | Microsoft Docs"
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
  - "BLOB-объект, извлечение"
  - "OLE DB, BLOB-объекты"
  - "получение BLOBs"
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Извлечение двоичного объекта (BLOB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлечь двоичный объект \(BLOB\) можно разными способами:  использовать **DBTYPE\_BYTES**, чтобы извлечь BLOB как последовательность байтов, либо использовать такой интерфейс, как `ISequentialStream`.  Дополнительные сведения см. в разделе [Объекты BLOB и COM](https://msdn.microsoft.com/en-us/library/ms711511.aspx) в *справочнике программиста OLE DB*.  
  
 В следующем примере демонстрируется, как извлечь объект BLOB с помощью методов интерфейса `ISequentialStream`.  Макрос [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md) позволяет указать интерфейс и флаги, используемые для этого интерфейса.  После открытия таблицы функция **Read** интерфейса `ISequentialStream` вызывается в цикле для последовательного извлечения байтов объекта BLOB.  Перед переходом к следующей записи с помощью функции `MoveNext` вызывается функция **Release**, освобождающая указатель интерфейса.  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories> > categories;  
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
  
 Дополнительные сведения о макросах, обрабатывающих данные BLOB, см. в подразделе "Макросы сопоставления столбцов" раздела [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md).  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)
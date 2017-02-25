---
title: "CLongBinary Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "BLOB"
  - "CLongBinary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB-объект"
  - "BLOB-объект, CLongBinary - класс"
  - "CLongBinary - класс"
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CLongBinary Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Simplifies работы с очень большие двоичные объекты часто Позвонимые данных \(Большим Двоичным Объектом или "большими двоичными объектами\) в базе данных.  
  
## Синтаксис  
  
```  
class CLongBinary : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CLongBinary::CLongBinary](../Topic/CLongBinary::CLongBinary.md)|Создает объект `CLongBinary`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CLongBinary::m\_dwDataLength](../Topic/CLongBinary::m_dwDataLength.md)|Содержит фактический размер в байтах объекта данных, дескриптор которого хранится в `m_hData`.|  
|[CLongBinary::m\_hData](../Topic/CLongBinary::m_hData.md)|Содержит маркер Windows `HGLOBAL` к фактическому объект изображения.|  
  
## Заметки  
 Например, запись поле в таблице SQL server может содержать растровое изображение, представляющий изображение.  Объект `CLongBinary` хранит такой объект и отслеживает его размера.  
  
> [!NOTE]
>  Как правило, лучше использовать [CByteArray](../../mfc/reference/cbytearray-class.md) использовать совместно с функцией [DFX\_Binary](../Topic/DFX_Binary.md).  Можно по\-прежнему использовать `CLongBinary`, но обычно `CByteArray` предоставляет больше функциональных возможностей в Win32, поскольку больше нет ограничений размера, присутствующего в 16\-разрядных `CByteArray`.  Эта консультация применяется к программированию с DAO \(DAO\), а также ODBC \(ODBC\).  
  
 Чтобы использовать объект `CLongBinary` объявите член данных поля типа `CLongBinary` в классе набора записей.  Этот элемент является внедренным членом класса набора записей и набор записей будет построен, когда будет создан.  После того как объект `CLongBinary` построен, механизм обмена полями записей \(RFX\) загружает объект данных из поля текущей записи в источнике данных и сохраняет его обратно к записи, когда запись будет обновлена.  RFX запрашивает источник данных для размера большого двоичного объекта, выберите хранилище для него \(с помощью элемента данных `m_hData` объекта `CLongBinary` \) и магазины дескриптор `HGLOBAL` к данным в `m_hData`.  RFX также хранит фактический размер объекта данных в элементе данных `m_dwDataLength`.  Работа с данными в объекте с помощью `m_hData`, используя те же методы, как правило, пользуются конструктором для работы с данными, хранящимися в маркере Windows `HGLOBAL`.  
  
 При разрушаете набор записей, внедренный объект `CLongBinary` также уничтожается, и его отмены выделения деструктора данные `HGLOBAL` обрабатывают.  
  
 Дополнительные сведения о больших объектах и использования `CLongBinary` см. в разделе статьи [набор записей \(ODBC\)](../../data/odbc/recordset-odbc.md) и [Набор записей. работа с большими элементами данных \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CLongBinary`  
  
## Требования  
 **Header:**  afxdb\_.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)
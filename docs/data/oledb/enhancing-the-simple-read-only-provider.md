---
title: "Усовершенствование простого поставщика только для чтения | Microsoft Docs"
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
  - "IRowsetLocate - класс"
  - "IRowsetLocate - класс, добавление в поставщики шаблонов OLE DB"
  - "поставщики только для чтения [C++]"
  - "простые поставщики только для чтения [C++]"
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Усовершенствование простого поставщика только для чтения
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В данном подразделе демонстрируется способ усовершенствования [простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md), созданного в предыдущем подразделе.  С помощью `IRowsetLocateImpl` создается реализация интерфейса `IRowsetLocate` и обеспечивается поддержка закладок.  
  
 После того как будет создан действующий поставщик, может потребоваться расширить его возможности для обеспечения обновления, обработки транзакций или повышения производительности алгоритма выборки строк.  Расширение возможностей поставщика, как правило, предполагает добавление интерфейса в существующий объект COM.  
  
 В примере, приведенном в следующих подразделах, производится усовершенствование механизма выборки строк путем добавления интерфейса `IRowsetLocate` в объект `CAgentRowset`.  В этих разделах описывается выполнение следующих операций:  
  
-   [Обеспечение наследования RMyProviderRowset от IRowsetLocate](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).  
  
-   [Динамическое определение столбцов, возвращаемых объекту\-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## См. также  
 [Создание простого поставщика только для чтения](../../data/oledb/creating-a-simple-read-only-provider.md)
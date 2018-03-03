---
title: "Набор записей: Работа с большими элементами данных (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf82e1fabd45e9bccd63e4ba46068b75d2c2a0a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Набор записей. Работа с большими элементами данных (ODBC)
Этот раздел относится к классам MFC ODBC и классы MFC DAO.  
  
> [!NOTE]
>  При использовании классов MFC DAO управление элементами больших объемов данных с помощью класса [CByteArray](../../mfc/reference/cbytearray-class.md) вместо класса [CLongBinary](../../mfc/reference/clongbinary-class.md). При использовании классов MFC ODBC с массовой выборке строк используйте `CLongBinary` вместо `CByteArray`. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Предположим, что базы данных можно хранить больших частей данных, таких как растровые изображения (фотографии сотрудников, карты, изображения продуктов, объекты OLE и т. д.). Этот тип данных часто называется большого двоичного объекта (или BLOB-ОБЪЕКТОВ) из-за:  
  
-   Каждое значение поля велик.  
  
-   В отличие от числа и других простых типов данных она имеет размер не прогнозируемого.  
  
-   Данные не имеют строгой формы, с точки зрения программы.  
  
 В этом разделе объясняется, какую поддержку классы баз данных предоставляют для работы с таких объектов.  
  
##  <a name="_core_managing_large_objects"></a>Управление большими объектами  
 Наборы записей имеет два способа устранения специальные сложность управления больших двоичных объектов. Можно использовать класс [CByteArray](../../mfc/reference/cbytearray-class.md) или можно использовать класс [CLongBinary](../../mfc/reference/clongbinary-class.md). В общем случае `CByteArray` является предпочтительным способом для управления большими двоичными данными.  
  
 `CByteArray`требуется больше ресурсов, чем `CLongBinary` , но более производительные, как описано в [сравнению с классом](#_core_the_cbytearray_class). `CLongBinary`в кратко описан [класс CLongBinary](#_core_the_clongbinary_class).  
  
 Подробные сведения об использовании `CByteArray` для работы с большими элементами данных. в разделе [Технические заметки 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_cbytearray_class"></a>Класс CByteArray  
 `CByteArray`является одним из классов коллекций MFC. Объект `CByteArray` объект сохраняет динамического массива байтов — при необходимости может расширяться массива. Этот класс предоставляет быстрый доступ по индексу, как и встроенные массивы C++. `CByteArray`объекты можно сериализовать и помещены в дамп для диагностики. Класс предоставляет функции-члены для получения и установки значений определенных байтов, Вставка добавления байтов и удаления одного или всех байтов. Эти средства сделать синтаксический анализ двоичных данных. Например если двоичный объект является объектом OLE, может потребоваться работы нескольких байтов заголовка для доступа к самому объекту.  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a>С помощью CByteArray в наборах записей  
 Предоставив элемента данных поля набора записей типа `CByteArray`, предоставления основных основы [RFX](../../data/odbc/record-field-exchange-rfx.md) можно управлять передачей такого объекта между набора записей и источником данных и с помощью которого можно управлять данные внутри объекта. RFX необходимо использовать специальный узел для хранения извлеченных данных, и вам необходим способ для доступа к данным.  
  
 Подробные сведения об использовании `CByteArray` для работы с большими элементами данных. в разделе [Технические заметки 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md).  
  
##  <a name="_core_the_clongbinary_class"></a>CLongBinary-класс  
 Объект [CLongBinary](../../mfc/reference/clongbinary-class.md) объект представляет собой простую оболочку `HGLOBAL` дескриптор блока памяти в куче. Во время привязки столбца таблицы, содержащего большой двоичный объект, RFX выделяет `HGLOBAL` обработки при передаче данных в набор записей, который сохраняется в `CLongBinary` поля в наборе записей.  
  
 В свою очередь, используется `HGLOBAL` обработки, `m_hData`, для работы с данными, как и для какого-либо данных обрабатывается. Это место, куда [CByteArray](../../mfc/reference/cbytearray-class.md) добавляет возможности.  
  
> [!CAUTION]
>  Объекты класса CLongBinary не может использоваться в качестве параметров в вызовах функций. Кроме того, их реализацию, которая вызывает **:: SQLGetData**, во всех случаях снижается производительность прокрутке для моментальных снимков. Это также может быть значение true при использовании **:: SQLGetData** вызывать для извлечения столбцов динамической схемы.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)
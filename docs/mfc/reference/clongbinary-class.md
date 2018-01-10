---
title: "CLongBinary-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs: C++
helpviewer_keywords: CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49661932192a32550d50edfbbc52d7967cb78dcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="clongbinary-class"></a>CLongBinary-класс
Упрощает работу с очень большими объектами двоичных данных (BLOB-объектами) в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Создает объект `CLongBinary`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Содержит фактический размер в байтах, дескриптор которого хранится в объект данных `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Содержит Windows `HGLOBAL` дескриптор объекта фактическим размерам изображения.|  
  
## <a name="remarks"></a>Примечания  
 Например поле записи в таблице SQL может содержать точечный рисунок, представляющий рисунок. Объект `CLongBinary` объект сохраняет такого объекта и отслеживает ее размер.  
  
> [!NOTE]
>  Как правило, является наилучшим решением теперь использовать [CByteArray](../../mfc/reference/cbytearray-class.md) в сочетании с [DFX_Binary](record-field-exchange-functions.md#dfx_binary) функции. Можно по-прежнему использовать `CLongBinary`, но в целом `CByteArray` предоставляет дополнительные функциональные возможности в Win32, так как она больше не ограничение размера, с 16-разрядное `CByteArray`. Эта рекомендация относится к программированию объектов доступа к данным (DAO), а также Open Database Connectivity (ODBC).  
  
 Для использования `CLongBinary` объекта, объявить элемент данных поля типа `CLongBinary` в классе набора записей. Этот член будет внедренного члена класса записей и будет создан при создании набора записей. После `CLongBinary` объект создан, механизм обмена (полями записей RFX) поле записи загружает объект данных из поля в текущей записи в источнике данных и сохраняет его обратно в записи, при обновлении записи. RFX запрашивает источник данных для размер большой двоичный объект выделяет память для него (через `CLongBinary` объекта `m_hData` элемент данных) и сохраняет `HGLOBAL` обработки данных в `m_hData`. RFX также хранит фактический размер объекта данных в `m_dwDataLength` элемент данных. Работа с данными в объекте через `m_hData`, используя те же техники, который обычно используется для обработки данных, хранящихся в Windows `HGLOBAL` обработки.  
  
 После уничтожения набора записей, встроенный `CLongBinary` объект также удаляется, и освобождает его деструктор `HGLOBAL` маркер данных.  
  
 Дополнительные сведения о больших объектов и использование `CLongBinary`, см. в статьях [записей (ODBC)](../../data/odbc/recordset-odbc.md) и [набор записей: работа с большой элементов данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb_.h  
  
##  <a name="clongbinary"></a>CLongBinary::CLongBinary  
 Создает объект `CLongBinary`.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 Хранит фактический размер в байтах данных, хранящихся в `HGLOBAL` обработки в `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот размер может быть меньше, чем размер блока памяти, выделенного для данных. Вызов Win32 [GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593) функции, чтобы получить выделенный размер.  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Сохраняет Windows `HGLOBAL` дескриптор фактический большой двоичный объект данных.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)

---
title: "CLongBinary-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object)
- CLongBinary class
- BLOB (binary large object), CLongBinary class
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bb73604ee4d15f3a71be8514f348ad265064928a
ms.lasthandoff: 02/24/2017

---
# <a name="clongbinary-class"></a>CLongBinary-класс
Упрощает работу с очень большими объектами двоичных данных (BLOB-объектами) в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Создает объект `CLongBinary`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Содержит реальный размер в байтах, дескриптор которого хранится в объект данных `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Содержит Windows `HGLOBAL` дескриптор объекта самого изображения.|  
  
## <a name="remarks"></a>Примечания  
 Например поле записи в таблице SQL может содержать точечный рисунок, представляющий изображение. Объект `CLongBinary` объект сохраняет такой объект и отслеживает его размер.  
  
> [!NOTE]
>  Как правило, это лучше теперь будет использовать [CByteArray](../../mfc/reference/cbytearray-class.md) в сочетании с [DFX_Binary](http://msdn.microsoft.com/library/678021a3-2e46-44d7-8528-71bb692dcc07) функции. Вы можете использовать `CLongBinary`, но в целом `CByteArray` предоставляет больше функциональных возможностей, в разделе Win32, так как нет больше не обнаружил 16-разрядных ограничение на размер `CByteArray`. Эта рекомендация относится к программированию с помощью объектов доступа к данным (DAO), а также Open Database Connectivity (ODBC).  
  
 Для использования `CLongBinary` объекта, объявить элемент данных поля типа `CLongBinary` в классе набора записей. Этот член будет внедренные элементы класса записей и будут созданы при создании набора записей. После `CLongBinary` объект создан, механизм обмена (полями записей RFX) поле записи загружает объект данных из поля в текущей записи в источнике данных и сохраняет его обратно к записи, при обновлении записи. RFX запрашивает источник данных размер большой двоичный объект выделяет память для него (через `CLongBinary` объекта `m_hData` элемент данных) и сохраняет `HGLOBAL` обработки данных в `m_hData`. RFX также хранит фактический размер объекта данных в `m_dwDataLength` элемент данных. Работа с данными в объекте через `m_hData`, с помощью тех же методов, обычно используется для обработки данных, хранящихся в Windows `HGLOBAL` обработки.  
  
 После удаления набора записей, встроенный `CLongBinary` объект также удаляется, и освобождает его деструктор `HGLOBAL` маркер данных.  
  
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
 Этот размер может быть меньше, чем размер блока памяти, выделенной для данных. Вызов Win32 [GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593) функции, чтобы получить выделенный размер.  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Windows хранит `HGLOBAL` дескриптор фактический большой двоичный объект данных.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)


---
title: Класс CLongBinary | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed0603482ffccf1bcb827d67b174768cfd3e3168
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196801"
---
# <a name="clongbinary-class"></a>Класс CLongBinary
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
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Содержит фактический размер в байтах для объекта данных, дескриптор которого хранится в `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Содержит дескриптор Windows HGLOBAL объекту фактическое изображение.|  
  
## <a name="remarks"></a>Примечания  
 Например поле записи в таблице SQL может содержать точечный рисунок, представляющий изображение. Объект `CLongBinary` объект сохраняет объект и отслеживает его размер.  
  
> [!NOTE]
>  Как правило, это лучше все-таки теперь использовать [CByteArray](../../mfc/reference/cbytearray-class.md) в сочетании с [DFX_Binary](record-field-exchange-functions.md#dfx_binary) функции. Вы можете продолжать использовать `CLongBinary`, но в целом `CByteArray` предоставляет дополнительные функциональные возможности в Win32, так как она не обнаружил 16-разрядное ограничение на размер `CByteArray`. Эта рекомендация относится к программированию с помощью объектов доступа к данным (DAO), а также Open Database Connectivity (ODBC).  
  
 Чтобы использовать `CLongBinary` объекта, объявить элемент данных поля типа `CLongBinary` в классе набора записей. Этот член будет внедренного члена класса записей и будут созданы при создании набора записей. После `CLongBinary` объект создан, механизм полями записей (RFX) exchange загружает объект данных из поля в текущей записи в источнике данных и сохраняет его обратно к записи, при обновлении записи. RFX запрашивает источник данных для размер большой двоичный объект выделяет память для него (через `CLongBinary` объекта `m_hData` элемент данных) и сохраняет `HGLOBAL` обработки данных в `m_hData`. RFX также хранит фактический размер объекта данных в `m_dwDataLength` элемент данных. Работа с данными в объекте через `m_hData`, используя те же способы, которые обычно используются для работы с данными, хранящихся в Windows `HGLOBAL` обработки.  
  
 Когда уничтожить набора записей, встроенный `CLongBinary` уничтожении объекта, и его деструктор освобождает `HGLOBAL` дескриптора данных.  
  
 Дополнительные сведения о больших объектов и использование `CLongBinary`, см. в статьях [записей (ODBC)](../../data/odbc/recordset-odbc.md) и [набор записей: работа с элементами больших данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb_.h  
  
##  <a name="clongbinary"></a>  CLongBinary::CLongBinary  
 Создает объект `CLongBinary`.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength  
 Хранит фактический размер в байтах данных, хранящихся в маркера HGLOBAL `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот размер может быть меньше, чем размер блока памяти, выделенного для данных. Вызов Win32 [GLobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize) функцию, чтобы получить выделенный размер.  
  
##  <a name="m_hdata"></a>  CLongBinary::m_hData  
 Сохраняет дескриптор Windows HGLOBAL фактический большой двоичный объект данных.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>См. также  
 [Класс CObject](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)

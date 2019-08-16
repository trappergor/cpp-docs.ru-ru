---
title: Класс CLongBinary
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: 94666c0d15898e05ae78663a15d86b7d00d5c9c6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505676"
---
# <a name="clongbinary-class"></a>Класс CLongBinary

Упрощает работу с очень большими объектами двоичных данных (BLOB-объектами) в базе данных.

## <a name="syntax"></a>Синтаксис

```
class CLongBinary : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CLongBinary:: CLongBinary](#clongbinary)|Создает объект `CLongBinary`.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Содержит фактический размер объекта данных в байтах, в `m_hData`котором хранится его обработчик.|
|[CLongBinary:: m_hData](#m_hdata)|Содержит обработчик ХГЛОБАЛ Windows для фактического объекта Image.|

## <a name="remarks"></a>Примечания

Например, поле записи в таблице SQL может содержать точечный рисунок, представляющий изображение. `CLongBinary` Объект хранит такой объект и отслеживает его размер.

> [!NOTE]
>  Как правило, рекомендуется использовать [CByteArray](../../mfc/reference/cbytearray-class.md) в сочетании с функцией [DFX_Binary](record-field-exchange-functions.md#dfx_binary) . Вы по-прежнему `CLongBinary`можете использовать, но `CByteArray` в целом предоставляет больше функциональных возможностей в Win32, так как отсутствует ограничение размера, обнаруженное 16- `CByteArray`разрядным. Это рекомендации применимы к программированию с помощью объектов доступа к данным (DAO) и ODBC.

Чтобы использовать `CLongBinary` объект, объявите элемент данных поля типа `CLongBinary` в классе набора записей. Этот член будет внедренным элементом класса Recordset и будет создан при создании набора записей. После создания `CLongBinary` объекта механизм обмена полями записей (RFX) загружает объект данных из поля текущей записи в источнике данных и сохраняет его обратно в запись при обновлении записи. RFX запрашивает у источника данных размер большого двоичного объекта `CLongBinary` , выделяет для него хранилище (через элемент `m_hData` данных объекта `HGLOBAL` ) и сохраняет в нем `m_hData`обработчик. RFX также хранит фактический размер объекта данных в `m_dwDataLength` элементе данных. Работа с данными в объекте `m_hData`с помощью тех же методов, которые обычно используются для работы с данными, хранящимися в обработчике Windows. `HGLOBAL`

При уничтожении набора записей внедренный `CLongBinary` объект также уничтожается, и его деструктор освобождает `HGLOBAL` маркер данных.

Дополнительные сведения о больших объектах и использовании `CLongBinary`см. в статье [набор записей (ODBC)](../../data/odbc/recordset-odbc.md) и [набор записей. Работа с большими элементами данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb_. h

##  <a name="clongbinary"></a>CLongBinary:: CLongBinary

Создает объект `CLongBinary`.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>CLongBinary:: m_dwDataLength

Сохраняет фактический размер в байтах данных, хранящихся в ХГЛОБАЛном маркере в `m_hData`.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Примечания

Этот размер может быть меньше, чем размер блока памяти, выделенного для данных. Вызовите функцию Win32 [глобалсизе](/windows/win32/api/winbase/nf-winbase-globalsize) , чтобы получить выделенный размер.

##  <a name="m_hdata"></a>CLongBinary:: m_hData

Сохраняет обработчик ХГЛОБАЛ Windows для фактических данных больших двоичных объектов.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)

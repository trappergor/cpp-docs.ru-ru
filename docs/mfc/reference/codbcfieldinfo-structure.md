---
title: Структура CODBCFieldInfo
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: bc2ad0c8319a60b773211dbd6b52b57bb2dbcafb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272767"
---
# <a name="codbcfieldinfo-structure"></a>Структура CODBCFieldInfo

`CODBCFieldInfo` Структура содержит сведения о полях в источник данных ODBC.

## <a name="syntax"></a>Синтаксис

```
struct CODBCFieldInfo
{
    CString m_strName;
    SWORD m_nSQLType;
    UDWORD m_nPrecision;
    SWORD m_nScale;
    SWORD m_nNullability;
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Имя поля.

*m_nSQLType*<br/>
Тип данных SQL поля. Это может быть типом данных ODBC SQL или типом данных специфические для драйвера SQL. Список допустимых типов данных ODBC SQL см. в разделе «Типы данных SQL» в пакете Windows SDK. Сведения о типах данных драйвера SQL см. в разделе документации по драйверу.

*m_nPrecision*<br/>
Максимальная точность поля. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в пакете Windows SDK.

*m_nScale*<br/>
Масштаб поля. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в пакете Windows SDK.

*m_nNullability*<br/>
Является ли поле допускает значение Null. Это может быть одно из двух значений: SQL_NULLABLE, если поле допускает значения Null, или SQL_NO_NULLS, если поле не принимает значения Null.

## <a name="remarks"></a>Примечания

Чтобы получить эти данные, вызовите [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)

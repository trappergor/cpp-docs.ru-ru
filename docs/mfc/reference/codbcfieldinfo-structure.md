---
title: Структура CODBCFieldInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1723e93320129fae232bb850caa123d1638a37b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853086"
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
 *m_strName*  
 Имя поля.  
  
 *m_nSQLType*  
 Тип данных SQL поля. Это может быть типом данных ODBC SQL или типом данных специфические для драйвера SQL. Список допустимых типов данных ODBC SQL см. в разделе «Типы данных SQL» в пакете Windows SDK. Сведения о типах данных драйвера SQL см. в разделе документации по драйверу.  
  
 *m_nPrecision*  
 Максимальная точность поля. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в пакете Windows SDK.  
  
 *m_nScale*  
 Масштаб поля. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в пакете Windows SDK.  
  
 *m_nNullability*  
 Является ли поле допускает значение Null. Это может быть одно из двух значений: SQL_NULLABLE, если поле допускает значения Null, или SQL_NO_NULLS, если поле не принимает значения Null.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить эти данные, вызовите [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)



---
title: Структура CODBCFieldInfo | Документы Microsoft
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
ms.openlocfilehash: 88bcac3c7ce4658ec7dafeaa1cac45b5f2450298
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370738"
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
 `m_strName`  
 Имя поля.  
  
 *m_nSQLType*  
 Тип данных SQL поля. Это может быть тип данных SQL драйвера или тип данных ODBC SQL. Список допустимых типов данных ODBC SQL в разделе «Типы данных SQL» в Windows SDK. Сведения о типах данных драйвера SQL см. в документации драйвера.  
  
 *m_nPrecision*  
 Максимальная точность поля. Дополнительные сведения см. в Windows SDK «Точность, масштаб, длину и отображаемый размер».  
  
 *m_nScale*  
 Масштаб поля. Дополнительные сведения см. в Windows SDK «Точность, масштаб, длину и отображаемый размер».  
  
 *m_nNullability*  
 Является ли поле допускает значение Null. Это может быть одно из двух значений: **SQL_NULLABLE** Если поле допускает значения Null, или **SQL_NO_NULLS** Если поле не может принимать значение Null.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить эти данные, вызовите [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)



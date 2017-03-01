---
title: "Структура CODBCFieldInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC, data source information
- CODBCFieldInfo structure
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
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
ms.openlocfilehash: 1080eb323c599014d84acab94aee4622795fdb96
ms.lasthandoff: 02/24/2017

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
 Тип данных поля SQL. Это может быть тип данных SQL драйвера или типу данных ODBC SQL. Перечень допустимых типов данных ODBC SQL см. в разделе «Типы данных SQL» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Сведения о типах данных SQL, специфические для драйвера драйвер документации.  
  
 *m_nPrecision*  
 Максимальная точность поля. Дополнительные сведения см. в разделе «Точность, масштаб, длина и отображаемый размер» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nScale*  
 Масштаб поля. Дополнительные сведения см. в разделе «Точность, масштаб, длина и отображаемый размер» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nNullability*  
 Является ли поле допускает значение Null. Это может быть одно из двух значений: **SQL_NULLABLE** Если поле может принимать значения Null или **SQL_NO_NULLS** Если поля не допускает значения Null.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить эти данные, вызовите [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)




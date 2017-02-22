---
title: "Структура CODBCFieldInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CODBCFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CODBCFieldInfo - структура"
  - "ODBC, сведения об источнике данных"
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Структура CODBCFieldInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CODBCFieldInfo` содержит сведения о полях в источнике данных ODBC.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `m_strName`  
 Имя поля.  
  
 *m\_nSQLType*  
 Тип данных SQL поля.  Это может быть типом данных ODBC SQL или типом данных SQL драйвер\- функции.  Типы данных SQL Для списка допустимых ODBC см. в разделе «типы данных SQL» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Дополнительные сведения о типах данных SQL драйвер\- см. в документации по драйвера.  
  
 *m\_nPrecision*  
 Максимальная точность поля.  Дополнительные сведения см. в разделе «точность, масштаб, длину, и размер отображения» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nScale*  
 Масштаб поля.  Дополнительные сведения см. в разделе «точность, масштаб, длину, и размер отображения» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nNullability*  
 Принимает ли поле значение NULL.  Это может быть одним из 2 значений: **SQL\_NULLABLE**, если поле допускает значения NULL, и значение **SQL\_NO\_NULLS**, если поле не допускает значения NULL.  
  
## Заметки  
 Для получения этих сведений вызовите метод [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md).  
  
## Требования  
 **Header:** afxdb.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)
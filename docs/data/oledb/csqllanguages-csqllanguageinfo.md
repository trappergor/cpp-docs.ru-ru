---
title: "CSQLLanguages, CSQLLanguageInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSQLLanguageInfo"
  - "m_szProgrammingLanguage"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szSource"
  - "m_szYear"
  - "CSQLLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSQLLanguageInfo - класс параметров"
  - "CSQLLanguages typedef - класс"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szProgrammingLanguage"
  - "m_szSource"
  - "m_szYear"
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CSQLLanguages, CSQLLanguageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовите **CSQLLanguages** класс typedef для реализации его класс **CSQLLanguageInfo** параметра.  
  
## Заметки  
 Дополнительные сведения см. в разделе [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) при использовании классов typedef.  
  
 Этот класс определяет уровни, параметры и диалекты соответствия поддерживаемые SQL. при обработке реализацией данные, определенные в каталоге.  
  
 В следующей таблице перечислены элементы данных класса и соответствующие столбцы OLE DB.  В разделе [Набор строк SQL\_LANGUAGES](https://msdn.microsoft.com/en-us/library/ms714374.aspx) справочника *программиста OLE DB* дополнительные сведения о схеме и столбцам.  
  
|Элементы данных|Столбцы OLE DB|  
|---------------------|--------------------|  
|m\_szSource|SQL\_LANGUAGE\_SOURCE|  
|m\_szYear|SQL\_LANGUAGE\_YEAR|  
|m\_szConformance|SQL\_LANGUAGE\_CONFORMANCE|  
|m\_szIntegrity|SQL\_LANGUAGE\_INTEGRITY|  
|m\_szImplementation|SQL\_LANGUAGE\_IMPLEMENTATION|  
|m\_szBindingStyle|SQL\_LANGUAGE\_BINDING\_STYLE|  
|m\_szProgrammingLanguage|SQL\_LANGUAGE\_PROGRAMMING\_LANGUAGE|  
  
## Требования  
 **Header:**  atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)
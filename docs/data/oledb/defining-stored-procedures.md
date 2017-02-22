---
title: "Определение хранимых процедур | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB, хранимые процедуры"
  - "хранимые процедуры, определение"
  - "хранимые процедуры, OLE DB"
  - "хранимые процедуры, синтаксис"
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Определение хранимых процедур
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Перед открытием хранимой процедуры необходимо сначала определить ее, используя макрос [DEFINE\_COMMAND](../../data/oledb/define-command.md).  После определения команды обозначьте параметры вопросительным знаком \(?\) в качестве маркера параметра:  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Обратите внимание, что синтаксис \(использование фигурных скобок и т. д.\), который используется в примерах кода этого раздела, характерен для SQL Server.  Синтаксис, используемый в хранимых процедурах, может отличаться в зависимости от поставщика.  
  
 Далее, в сопоставлении параметров укажите параметры, которые были использованы в командах, перечисляя их согласно заданному в команде порядку:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 Предыдущий пример иллюстрируют порядок расположения хранимой процедуры.  Обычно для эффективного многократного применения кода база данных имеет предопределенный набор хранимых процедур под названием "Sales by Year" или "dt\_adduserobject". Список определений можно просмотреть с помощью программы SQL Server Enterprise Manager.  Список можно открывать следующим образом \(расположение параметров "?" зависит от интерфейса хранимых процедур\).  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Объявите класс команды.  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor> >  
```  
  
 В конечном счете, вызовите хранимые процедуры `OpenRowset` следующим образом:  
  
```  
CSession m_session;  
HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor> >::Open(m_session);  
}  
```  
  
 Убедитесь в том, что хранимые процедуры определяются с помощь атрибутов базы данных [db\_command](../../windows/db-command.md) способом, приведенным ниже:  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## См. также  
 [Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)
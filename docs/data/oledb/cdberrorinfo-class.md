---
title: "Класс CDBErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo"
  - "ATL::CDBErrorInfo"
  - "ATL.CDBErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBErrorInfo - класс"
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CDBErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает поддержку обработки ошибок OLE DB с помощью интерфейса OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx).  
  
## Синтаксис  
  
```  
class CDBErrorInfo  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Возвращает все сведения об ошибке, содержащиеся в записи ошибок.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Вызывает функцию [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) для получения основных сведений о конкретной ошибке.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Вызывает метод [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx), чтобы вернуть указатель на интерфейс объекта настраиваемой ошибки.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Вызывает метод [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx), чтобы вернуть указатель интерфейса **IErrorInfo** к конкретной записи.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Вызывает функцию [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) для получения параметров ошибки.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Получает записи ошибок для указанного объекта.|  
  
## Заметки  
 Этот интерфейс возвращает одну или несколько записей ошибок для пользователя.  Сначала вызовите метод [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md), чтобы получить количество записей ошибок.  Затем вызовите одну из функций доступа, например [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md) для получения сведений об ошибке для каждой записи.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
---
title: "Добавление интерфейса в поставщик | Microsoft Docs"
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
  - "шаблоны поставщика OLE DB, интерфейсы объектов"
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Добавление интерфейса в поставщик
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Следует определить, в какой объект требуется добавить интерфейс \(обычно это объект источника данных, набора строк, команды или сеанса, созданный мастером поставщика OLE DB\).  Возможно, объект, в который требуется добавить интерфейс, не поддерживается поставщиком.  В этом случае для создания объекта необходимо запустить мастер поставщика OLE DB библиотеки ATL.  Щелкните правой кнопкой мыши проект в представлении классов, выберите пункт **Добавить класс** в меню **Добавить**, а затем выберите пункт **Поставщик OLEDB библиотеки ATL**.  Возможно, потребуется разместить код интерфейса в отдельном каталоге и затем скопировать файлы в проект поставщика.  
  
 Если создан новый класс для поддержки интерфейса, следует наследовать объект от этого класса.  Например, можно добавить класс **IRowsetIndexImpl** в объект набора строк:  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 Добавьте интерфейс в **COM\_MAP** объекта с помощью макроса COM\_INTERFACE\_ENTRY.  Если файл сопоставления отсутствует, его необходимо создать.  Примеры.  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Для объекта набора строк следует связать сопоставление родительского объекта, чтобы объект смог предоставить делегата для родительского класса.  В этом примере добавьте макрос COM\_INTERFACE\_ENTRY\_CHAIN в сопоставление:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
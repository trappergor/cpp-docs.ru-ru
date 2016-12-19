---
title: "CUtlProps::OnInterfaceRequested | Microsoft Docs"
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
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnInterfaceRequested - метод"
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::OnInterfaceRequested
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обрабатывает запросы для дополнительного интерфейса, когда объект\-получатель вызывает метод для одного из интерфейсов поколения объектов.  
  
## Синтаксис  
  
```  
  
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(  
   REFIID riid  
);  
```  
  
#### Параметры  
 `riid`  
 \[in\] идентификатор IID для запрошенного интерфейса.  Дополнительные сведения см. в описании параметра `riid``ICommand::Execute` справочника *программиста OLE DB* \(в *MDAC SDK*\).  
  
## Заметки  
 **OnInterfaceRequested**  обрабатывает запросы объект\-получателя для дополнительного интерфейса, когда объект\-получатель вызывает метод для одного из интерфейсов создания объектов \(например, **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset` или `ICommand`\).  Он устанавливает соответствующие свойства OLE DB для запрошенного интерфейса.  Например, если запросы **IID\_IRowsetLocate** объект\-получателя, **OnInterfaceRequested** задает интерфейс **DBPROP\_IRowsetLocate**.  Этот прием поддерживает правильное состояния во время создания набора строк.  
  
 Этот метод вызывается, когда объект\-получатель вызывает метод **IOpenRowset::OpenRowset** или `ICommand::Execute`.  
  
 Если объект\-получатель будет открыт объект и запросы необязательный интерфейс, поставщик должен установить свойство, связанной с этим интерфейсом к `VARIANT_TRUE`.  Чтобы разрешить свойств для обработки, метод **OnInterfaceRequested**  вызывается перед вызовом метода **Выполнить**  поставщика вызывается.  По умолчанию **OnInterfaceRequested**  обрабатывает следующие интерфейсы:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 Если вы хотите обработать другие интерфейсы, переопределите этой функции в источнике данных, сеансе команде, или класс набора строк в отростчатым функциям.  Переопределенный должно пройти через обычный набор и задает, что интерфейсы свойств гарантирует, что настройки свойств также задает все свойства прикованные \(см. [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)\).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)
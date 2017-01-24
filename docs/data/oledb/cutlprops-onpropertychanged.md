---
title: "CUtlProps::OnPropertyChanged | Microsoft Docs"
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
  - "OnPropertyChanged"
  - "CUtlProps.OnPropertyChanged"
  - "CUtlProps::OnPropertyChanged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnPropertyChanged - метод"
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::OnPropertyChanged
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывается после установки свойства дескриптора приковал свойства.  
  
## Синтаксис  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### Параметры  
 `iCurSet`  
 Индекс массива набора свойств; ноль, если только один набор свойств.  
  
 `pDBProp`  
 Идентификатор свойства и новое значение в структуре [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx).  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  Возвращаемое значение по умолчанию `S_OK`.  
  
## Заметки  
 Если необходимо обработать прикованные свойства, например закладки или обновления, значения зависят от других значения свойства, необходимо переопределить этой функции.  
  
## Пример  
 В этой функции, пользователь получает идентификатор свойства из параметра `DBPROP*`.  Теперь, можно сравнить с идентификатор свойства для сцепления блоков.  Если свойство найдено, `SetProperties` называется со свойством, теперь устанавливается вместе с другим свойством.  В этом случае, если он получает `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS` или свойство `DBPROP_ORDEREDBOOKMARKS`, одно может задать свойство `DBPROP_BOOKMARKS`.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/CPP/cutlprops-onpropertychanged_1.h)]  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CUtlProps](../../data/oledb/cutlprops-class.md)
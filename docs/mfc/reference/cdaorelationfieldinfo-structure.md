---
title: "Структура CDaoRelationFieldInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoRelationFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationFieldInfo - структура"
  - "доступ к данным DAO.NET, Коллекция отношений"
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Структура CDaoRelationFieldInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CDaoRelationFieldInfo` содержит сведения о поле в отношении указанной \(DAO\) для объектов доступа к данным.  
  
## Синтаксис  
  
```  
  
      struct CDaoRelationFieldInfo  
{  
   CString m_strName;           // Primary  
   CString m_strForeignName;    // Primary  
};  
```  
  
#### Параметры  
 `m_strName`  
 Имя поля в главной таблице связи.  
  
 `m_strForeignName`  
 Имя поля во внешней таблице в связи.  
  
## Заметки  
 Объект связи DAO определяет поля в главной таблице и поля во внешней таблице, определяют связь.  Ссылки на основной в определении структуры предыдущем показывают, как сведения возвращаются в виде члена `m_pFieldInfos` объекта [CDaoRelationInfo](../Topic/CDaoRelationInfo%20Structure.md) полученного, вызвав функцию\-член [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) класса `CDaoDatabase`.  
  
 Объекты и объекты связи поля связи не представлены классом MFC.  Вместо этого объекты DAO основного объекты в основе MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) содержат коллекцию объектов связи, которая коллекция связей.  Каждый объект связи, в свою очередь, содержит коллекцию объектов поля связи.  Каждый объект поля связи сопоставляет поле в главной таблице с полем во внешней таблице.  Принято вместе объекты поля связи определяет группирование в составе поля в каждой таблице, которые вместе определяют связь.  `CDaoDatabase` позволяет получать объекты связи с объектом `CDaoRelationInfo` путем вызова функции\-члена `GetRelationInfo`.  Объект `CDaoRelationInfo`, затем, имеет элемент данных, `m_pFieldInfos`, указывает на массив объектов `CDaoRelationFieldInfo`.  
  
 Вызовите функцию\-член [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md), содержащий объекта `CDaoDatabase` в связях которого хранится коллекция объект соединения, которую поставщикам.  Затем обратиться к элементу `m_pFieldInfos` объекта [CDaoRelationInfo](../Topic/CDaoRelationInfo%20Structure.md).  `CDaoRelationFieldInfo` также определяет функции\-члена `Dump` выполняется в режиме построения.  Можно использовать `Dump` сбросить содержимое объекта `CDaoRelationFieldInfo`.  
  
## Требования  
 **Header:** afxdao.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура CDaoRelationInfo](../Topic/CDaoRelationInfo%20Structure.md)
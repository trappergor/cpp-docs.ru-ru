---
title: "Структура CDaoParameterInfo | Microsoft Docs"
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
  - "CDaoParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoParameterInfo - структура"
  - "доступ к данным DAO.NET, Parameters - коллекция"
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура CDaoParameterInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CDaoParameterInfo` содержит сведения о конкретном объекте параметров \(DAO\) для объектов доступа к данным.  
  
## Синтаксис  
  
```  
  
      struct CDaoParameterInfo  
{  
   CString m_strName;       // Primary  
   short m_nType;           // Primary  
   ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### Параметры  
 `m_strName`  
 Уникальные имена объект параметров.  Дополнительные сведения см. в разделе «свойство» Имя» в справке DAO.  
  
 `m_nType`  
 Значение, которое указывает тип данных объектов параметров.  Возможные значения Для списка участников `m_nType` структуры, см. в разделе [CDaoFieldInfo](../Topic/CDaoFieldInfo%20Structure.md).  Дополнительные сведения см. в разделе «свойство типа» в справке DAO.  
  
 *m\_varValue*  
 Значение параметра, хранящийся в объекте [COleVariant](../../mfc/reference/colevariant-class.md).  
  
## Заметки  
 Ссылки на первичное и дополнительное описанный выше показано, как сведения возвращаются функцией\-членом [GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) в классе `CDaoQueryDef`.  
  
 MFC не инкапсулирует объекты параметров DAO в классе.  Объекты DAO QueryDef основного объекты в основе MFC `CDaoQueryDef` хранятся параметры их в коллекциях параметров.  Для получения объектов параметров в объекте [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md), вызовите функцию\-член `GetParameterInfo` объекта QueryDef для определенного имени параметра или индекса в коллекцию параметров.  Можно использовать функцию\-член [CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md) вместе с `GetParameterInfo` итерации коллекции параметров.  
  
 Сведения, функцией\-членом [CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) хранятся в структуре `CDaoParameterInfo`.  Вызовите `GetParameterInfo` для объекта QueryDef которого в коллекции параметров хранится объект параметров.  
  
> [!NOTE]
>  Если требуется получить или задать только значение параметра, используйте функций\-членов [GetParamValue](../Topic/CDaoRecordset::GetParamValue.md) и [SetParamValue](../Topic/CDaoRecordset::SetParamValue.md) класса `CDaoRecordset`.  
  
 `CDaoParameterInfo` также определяет функции\-члена `Dump` выполняется в режиме построения.  Можно использовать `Dump` сбросить содержимое объекта `CDaoParameterInfo`.  
  
## Требования  
 **Header:** afxdao.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)
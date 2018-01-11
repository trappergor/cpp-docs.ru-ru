---
title: "Структура CDaoRelationFieldInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoRelationFieldInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8b9d27154608a19da1e575a46ec424f11eec2e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaorelationfieldinfo-structure"></a>Структура CDaoRelationFieldInfo
`CDaoRelationFieldInfo` Структура содержит сведения о поле в связь, определенную для объекты доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Имя поля в таблице первичного отношения.  
  
 `m_strForeignName`  
 Имя поля в таблице внешнего отношения.  
  
## <a name="remarks"></a>Примечания  
 Объект relation DAO задает поля основной таблицы и поля во внешней таблице, которые определяют связи. Ссылки на основном в определение структуры выше указывают, как данные возвращаются в `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта, полученного путем вызова [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)функции-члена класса `CDaoDatabase`.  
  
 Класс MFC не представлены отношения объекты и отношения объектов полей. Вместо этого DAO объекты базовых объектов MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) содержать коллекцию объектов отношения, называется коллекции отношений. Каждый объект отношения в свою очередь, содержит коллекцию объектов полей отношения. Каждый объект relation поля сопоставлены поля в таблице внешнего поля в таблице первичного. В совокупности объектов полей отношения Определите группу полей в каждой таблице, которые вместе определяют связи. `CDaoDatabase`позволяет выполнять доступ к связи объектов с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функции-члена. `CDaoRelationInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, которая указывает на массив `CDaoRelationFieldInfo` объектов.  
  
 Вызовите [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функция-член, содержащая `CDaoDatabase` объекта в объект связи, которые вас интересуют которого хранятся отношения является коллекция. Затем получить доступ к `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта. `CDaoRelationFieldInfo`также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoRelationFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)

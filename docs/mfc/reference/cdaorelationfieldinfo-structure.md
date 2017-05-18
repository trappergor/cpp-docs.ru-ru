---
title: "Структура CDaoRelationFieldInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 23d7497502f611cf2311e574556186dc5f7c7d3d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationfieldinfo-structure"></a>Структура CDaoRelationFieldInfo
`CDaoRelationFieldInfo` Структура содержит сведения о поле в связь, определенную для объектов доступа к данным (DAO).  
  
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
 Объект relation DAO задает поля в главной таблицы и поля во внешней таблице, которые определяют связи. Ссылки на определение структуры выше в основном указывают, как данные возвращаются в `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта, полученного путем вызова [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена класса `CDaoDatabase`.  
  
 Класс MFC не представлены связи и отношения поле объекты. Вместо этого DAO объекты базового MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) содержит коллекцию объектов отношения с именем коллекции отношений. Каждый объект отношения в свою очередь, содержит коллекцию объектов полей отношения. Каждый объект отношения поле сопоставляет поля в таблице первичного с полем во внешней таблице. Взятые вместе, объектов полей отношения определяют группу полей в каждой таблице которых совместно определяют связи. `CDaoDatabase`обращение к связи объектов с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функции-члена. `CDaoRelationInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, который указывает на массив `CDaoRelationFieldInfo` объектов.  
  
 Вызов [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена, содержащего `CDaoDatabase` объекта в объект отношения, вы заинтересованы в которого хранятся отношения является коллекция. Получить доступ к `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта. `CDaoRelationFieldInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoRelationFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)


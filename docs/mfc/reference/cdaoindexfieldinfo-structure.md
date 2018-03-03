---
title: "Структура CDaoIndexFieldInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b745a6f450bdf96389f49c673dc623b614e04db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoindexfieldinfo-structure"></a>Структура CDaoIndexFieldInfo
`CDaoIndexFieldInfo` Структура содержит сведения об объекте индекс поля, определенные для объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Однозначно называет объект полей индекса. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 *m_bDescending*  
 Указывает индекс порядок определяется объект индекса. **Значение TRUE,** Если по убыванию.  
  
## <a name="remarks"></a>Примечания  
 Индекс объекта могут иметь несколько полей, позволяющее определить, какие поля на индексируется tabledef (или набора записей на основе таблицы). Ссылки на основные выше указывают, как данные возвращаются в `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта, полученного путем вызова `GetIndexInfo` функции-члена класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Класс MFC не представлены объекты индекса и полей индекса. Вместо этого DAO объекты базовых объектов MFC класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержать коллекцию объектов индекса, который называется коллекции индексов. Каждый объект индекса, в свою очередь, содержит коллекцию объектов полей. Эти классы предоставьте функции-члены для доступа к отдельным элементам данных индекса, или можно получить доступ к их все одновременно с `CDaoIndexInfo` путем вызова метода `GetIndexInfo` функции-члена вмещающего объекта. `CDaoIndexInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, которая указывает на массив `CDaoIndexFieldInfo` объектов.  
  
 Вызовите `GetIndexInfo` функции-члена вмещающего объекта tabledef или набора записей, в чьи индексы будут коллекция является хранимых объект индекса, которые вас интересуют. Затем получить доступ к `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта. Длина `m_pFieldInfos` массива сохраняется в `m_nFields`. `CDaoIndexFieldInfo`также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoIndexFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)


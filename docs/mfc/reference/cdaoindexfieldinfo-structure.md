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
- CDaoIndexFieldInfo structure
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
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
ms.openlocfilehash: 975b3a704936adc9d4205938bb2c757ab650f0d9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
 Дает уникальное название поля объекта индекса. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 *m_bDescending*  
 Указывает индекс упорядочение определяется объект индекса. **Значение TRUE,** Если по убыванию.  
  
## <a name="remarks"></a>Примечания  
 Объект индекса может иметь несколько полей, позволяющее определить, какие поля на индексируется tabledef (или набора записей на основе таблицы). Ссылки на основной выше указывают, как данные возвращаются в `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта, полученного путем вызова `GetIndexInfo` функции-члена класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Класс MFC не представлены объекты индекса и полей индекса. Вместо этого DAO объекты базового MFC класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержит коллекцию объектов индекс с именем коллекции индексов. Каждый объект индекса, в свою очередь, содержит коллекцию объектов полей. Эти классы предоставить функции-члены для доступа к отдельным элементам данных индекса, или использовать их все одновременно с `CDaoIndexInfo` путем вызова метода `GetIndexInfo` функцию-член вмещающего объекта. `CDaoIndexInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, который указывает на массив `CDaoIndexFieldInfo` объектов.  
  
 Вызов `GetIndexInfo` функцию-член вмещающего объекта tabledef или набора записей, в которых индексы коллекция является хранятся объект индекса, который вас интересует. Получить доступ к `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта. Длина `m_pFieldInfos` массива сохраняется в `m_nFields`. `CDaoIndexFieldInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoIndexFieldInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)



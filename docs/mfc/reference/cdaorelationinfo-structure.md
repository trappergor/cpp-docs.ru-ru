---
title: "Структура CDaoRelationInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
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
ms.openlocfilehash: 7c3a8195aed2c3b3fe5c78c98afcc6e72a83cc21
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationinfo-structure"></a>Структура CDaoRelationInfo
`CDaoRelationInfo` Структура содержит сведения о связи, определенные между полями из двух таблиц в [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Дает уникальное название объект отношения. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 *m_strTable*  
 Имя главной таблицы в связи.  
  
 *m_strForeignTable*  
 Имя внешней таблице в связи. Внешние таблицы — это таблица, содержит внешние ключи. Как правило внешний таблица используется для наложения ссылочной целостности. Внешняя таблица обычно находится на стороне "многие" отношения «один ко многим». Примеры внешних таблиц: таблицы, содержащие коды для штатов США или коды городов Канады или заказов.  
  
 `m_lAttributes`  
 Содержит сведения о типе связи. Значение этого элемента может быть одно из следующих:  
  
- **dbRelationUnique** отношения один к одному.  
  
- **dbRelationDontEnforce** связь не применяется (не ссылочной целостности).  
  
- **dbRelationInherited** существует связь в долгосрочной базы данных, который содержит две вложенные таблицы.  
  
- **dbRelationLeft** связь является левое соединение. Левое внешнее соединение включает все записи из первой (левой) таблицы, даже если не соответствуют записям во второй таблице (справа).  
  
- **dbRelationRight** связь является объединением справа. Правое внешнее соединение включает все записи из второй (правой) таблицы, даже если не соответствуют записям в первой (левой) таблицы.  
  
- **dbRelationUpdateCascade** обновления происходит каскадом.  
  
- **dbRelationDeleteCascade** удаления происходит каскадом.  
  
 `m_pFieldInfos`  
 Указатель на массив [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) структуры. Массив содержит один объект для каждого поля в связи. `m_nFields` Элемент данных дает число элементов массива.  
  
 `m_nFields`  
 Число `CDaoRelationFieldInfo` объектов в `m_pFieldInfos` элемент данных.  
  
## <a name="remarks"></a>Примечания  
 Ссылки на первичной и вторичной выше указывают, как возвращаются сведения по [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена в классе `CDaoDatabase`.  
  
 Класс MFC не представлены отношения объектов. Вместо этого, объект DAO базового объекта MFC `CDaoDatabase` класс поддерживает коллекцию объектов отношения: `CDaoDatabase` предоставляет функции-члены для доступа к некоторых отдельных элементов, сведения о связях, или доступ к ним одновременно с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функцию-член вмещающего объекта базы данных.  
  
 Данные, полученные по [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена хранится в `CDaoRelationInfo` структуру. `CDaoRelationInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoRelationInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структура CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)


---
title: Структура CDaoRelationInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 112af640d020dc579c1ec2b1b7eace509daa451e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366266"
---
# <a name="cdaorelationinfo-structure"></a>Структура CDaoRelationInfo
`CDaoRelationInfo` Структура содержит сведения о связи, определенные между двумя таблицами в поля [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.  
  
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
 Однозначно называет объект отношения. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 *m_strTable*  
 Имена главной таблицы в связи.  
  
 *m_strForeignTable*  
 Имена внешней таблице в связи. Внешние таблицы — это таблица, используется для включения внешних ключей. Как правило используется внешней таблицы для наложения ссылочной целостности. Внешняя таблица обычно находится на стороне "многие" связи "один ко многим". Внешние таблицы примеры таблиц, содержащих коды для штатов США или Канады республики или заказов клиента.  
  
 `m_lAttributes`  
 Содержит сведения о типе связи. Значение этого элемента может быть одно из следующих:  
  
- **dbRelationUnique** связи один к одному.  
  
- **dbRelationDontEnforce** отношение не будет принудительно (целостность данных).  
  
- **dbRelationInherited** существует связь в долгосрочной базы данных, который содержит две вложенные таблицы.  
  
- **dbRelationLeft** связь является левое соединение. Левое внешнее соединение включает все записи из первого (слева) таблицы, даже если нет совпадающих значений для записей во второй таблице (справа).  
  
- **dbRelationRight** связь является правой соединения. Правое внешнее соединение включает все записи из второй (правый) таблицы, даже если отсутствуют соответствующие значения для записи в первой таблице (слева).  
  
- **dbRelationUpdateCascade** обновления происходит каскадом.  
  
- **dbRelationDeleteCascade** удаления происходит каскадом.  
  
 `m_pFieldInfos`  
 Указатель на массив [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) структуры. Массив содержит один объект для каждого поля в связи. `m_nFields` Элемент данных дает число элементов массива.  
  
 `m_nFields`  
 Число `CDaoRelationFieldInfo` объекты в `m_pFieldInfos` элемент данных.  
  
## <a name="remarks"></a>Примечания  
 Ссылки на первичной и вторичной выше указывают, как возвращаются сведения по [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена в классе `CDaoDatabase`.  
  
 Класс MFC не представлены отношения объектов. Вместо этого, объект DAO, базовый объект MFC `CDaoDatabase` класс содержит коллекцию объектов отношения: `CDaoDatabase` предоставляет функции-члены для некоторых отдельных элементов данных о связях, или доступ к ним можно обращаться за один раз с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функции-члена вмещающего объекта базы данных.  
  
 Сведений, получаемых методом [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функции-члена хранится в `CDaoRelationInfo` структуры. `CDaoRelationInfo` также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoRelationInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структура CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)

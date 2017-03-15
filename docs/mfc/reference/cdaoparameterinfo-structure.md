---
title: "Структура CDaoParameterInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b41d26b736ea9f84c53f71dbd71949f74fb8ae52
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoparameterinfo-structure"></a>Структура CDaoParameterInfo
`CDaoParameterInfo` Структура содержит сведения о объект параметра, определенные для объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Дает уникальное название объект параметра. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 `m_nType`  
 Значение, указывающее тип данных объекта parameter. Список возможных значений см. в разделе `m_nType` членом [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.  
  
 *m_varValue*  
 Значение параметра, хранятся в [COleVariant](../../mfc/reference/colevariant-class.md) объекта.  
  
## <a name="remarks"></a>Примечания  
 Ссылки на первичной и вторичной выше указывают, как возвращаются сведения по [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функции-члена в классе `CDaoQueryDef`.  
  
 MFC не инкапсулировать объекты DAO параметра в классе. Объекты DAO querydef MFC базового `CDaoQueryDef` объекты хранят параметры в коллекциях параметров. Доступ к объектам параметра в [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) объекта, вызов объекта querydef `GetParameterInfo` функции-члена имя определенного параметра или индекса в коллекции параметров. Можно использовать [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) функции-члена в сочетании с `GetParameterInfo` перебрать коллекцию параметров.  
  
 Данные, полученные по [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функции-члена хранится в `CDaoParameterInfo` структуру. Вызов `GetParameterInfo` для объекта querydef, в которых коллекции параметров хранится объект параметра.  
  
> [!NOTE]
>  Если вы хотите получить или задать значение параметра, используйте [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) и [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) функции-члены класса `CDaoRecordset`.  
  
 `CDaoParameterInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoParameterInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)


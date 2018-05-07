---
title: CTranslations, CTranslationInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szCatalog
- m_szSourceCatalog
- m_szTargetSchema
- m_szTargetCatalog
- m_szTargetName
- CTranslationInfo
- m_szSourceName
- m_szSchema
- CTranslations
- m_szName
- m_szSourceSchema
dev_langs:
- C++
helpviewer_keywords:
- m_szSourceSchema
- m_szSourceCatalog
- m_szSchema
- m_szTargetName
- m_szSourceName
- CTranslations typedef class
- m_szCatalog
- m_szTargetCatalog
- m_szName
- CTranslationInfo parameter class
- m_szTargetSchema
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 95bcede95c8d5de4f2c0e529a16e06277ac3240d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ctranslations-ctranslationinfo"></a>CTranslations, CTranslationInfo
Вызовите typedef-класс **CTranslations** реализации класса своего параметра **CTranslationInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс указывает преобразования символов, определенные в каталоге, доступных данному пользователю.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [переводы строк](https://msdn.microsoft.com/en-us/library/ms725365.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|TRANSLATION_CATALOG|  
|m_szSchema|TRANSLATION_SCHEMA|  
|m_szName|TRANSLATION_NAME|  
|m_szSourceCatalog|SOURCE_CHARACTER_SET_CATALOG|  
|m_szSourceSchema|SOURCE_CHARACTER_SET_SCHEMA|  
|m_szSourceName|SOURCE_CHARACTER_SET_NAME|  
|m_szTargetCatalog|TARGET_CHARACTER_SET_CATALOG|  
|m_szTargetSchema|TARGET_CHARACTER_SET_SCHEMA|  
|m_szTargetName|TARGET_CHARACTER_SET_NAME|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [CatDB](../../visual-cpp-samples.md)   
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)
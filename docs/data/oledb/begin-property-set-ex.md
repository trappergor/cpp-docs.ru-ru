---
title: "BEGIN_PROPERTY_SET_EX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPERTY_SET_EX
dev_langs: C++
helpviewer_keywords: BEGIN_PROPERTY_SET_EX macro
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ede0dac08233d82decb23064e47b61cbd9a05da1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropertysetex"></a>BEGIN_PROPERTY_SET_EX
Отмечает начало свойства задайте в свойстве значение карты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### <a name="parameters"></a>Параметры  
 `guid`  
 [in] Свойство идентификатора GUID.  
  
 `flags`  
 [in] **UPROPSET_HIDDEN** для всех наборов свойств, не требуется, чтобы предоставить доступ, или **UPROPSET_PASSTHROUGH** для поставщика, предоставление доступа к свойствам, определенные вне области поставщика.  
  
## <a name="example"></a>Пример  
 См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
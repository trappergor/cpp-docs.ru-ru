---
title: "ICommandTextImpl::GetCommandText | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
dev_langs: C++
helpviewer_keywords: GetCommandText method
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: df72d8d6e5c3c5c85d1216bf321216aef515a1d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="icommandtextimplgetcommandtext"></a>ICommandTextImpl::GetCommandText
Возвращает текст команды, заданные последнего вызова [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) в *справочника программиста OLE DB*. *PguidDialect* параметр учитывается по умолчанию.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)
---
title: "CDBPropSet::AddProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs: C++
helpviewer_keywords: AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa9c2d979bc98ebac543f0b17c7afdce2ab5f59b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
Добавляет свойство в наборе свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *dwPropertyID*  
 [in] Идентификатор добавляемого свойства. Используется для инициализации **dwPropertyID** из `DBPROP` структуры добавляются в набор свойств.  
  
 `var`  
 [in] Значение типа variant, используемый для инициализации значение свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 `szValue`  
 [in] Строка, используемая для инициализации значения свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 `bValue`  
 [in] Объект **БАЙТОВ** или логическое значение, используемое для инициализации значения свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 `nValue`  
 [in] Целочисленное значение, используемый для инициализации значение свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 *fltValue*  
 [in] Значение с плавающей запятой, используемый для инициализации значение свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 `dblValue`  
 [in] Значение с плавающей запятой двойной точности, используемый для инициализации значение свойства для `DBPROP` структуры добавляются в набор свойств.  
  
 `cyValue`  
 [in] CY значения валюты, используемой для инициализации значение свойства для `DBPROP` структуры добавляются в набор свойств.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** свойство был успешно добавлен. в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDBPropSet-класс](../../data/oledb/cdbpropset-class.md)   
 [Структуры DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)
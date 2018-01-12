---
title: "CRestrictions::Open | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbb0b175a6fa5a6cf93b4fe107884d5bb84f2487
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crestrictionsopen"></a>CRestrictions::Open
Возвращает результирующий набор, в соответствии с ограничения, предоставленное пользователем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `session`  
 [in] Указывает существующий объект сеанса, используемый для подключения к источнику данных.  
  
 *lpszParam*  
 [in] Указывает ограничения в наборе строк схемы.  
  
 `bBind`  
 [in] Указывает, нужно ли привязывать сопоставление столбцов автоматически. Значение по умолчанию — **true**, вследствие чего сопоставление столбцов автоматически привязываться. Установка `bBind` для **false** предотвращает автоматическое привязку сопоставление столбцов, таким образом, можно привязать вручную. (Ручной привязки — особый интерес для пользователей OLAP).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Можно указать максимум семь ограничения в наборе строк схемы.  
  
 В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) сведения об определенных ограничениях для каждого набора строк схемы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)   
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)
---
title: "BEGIN_ACCESSOR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BEGIN_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 39307534a9622160d6620b8d1c501cb112dbc717
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="beginaccessor"></a>BEGIN_ACCESSOR
Отмечает начало запись метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BEGIN_ACCESSOR(num, bAuto)  
```  
  
#### <a name="parameters"></a>Параметры  
 *num*  
 [in] Номер нуля смещение для метода доступа в этой карте метода доступа.  
  
 *кнопкой мыши*  
 [in] Указывает, является ли этот метод доступа автоматического доступа или метода доступа вручную. Если **true**, метод доступа доступен автоматически; Если **false**, метод доступа вручную. Метод автоматического доступа означает, что данные извлекаются для вас на операции перемещения.  
  
## <a name="remarks"></a>Примечания  
 В случае использования нескольких методов доступа в наборе строк, необходимо указать `BEGIN_ACCESSOR_MAP` и использовать `BEGIN_ACCESSOR` макрос для каждого отдельного метода доступа. Макрос `BEGIN_ACCESSOR` выполняется с помощью макроса `END_ACCESSOR` . `BEGIN_ACCESSOR_MAP` Завершилась макрос `END_ACCESSOR_MAP` макрос.  
  
## <a name="example"></a>Пример  
 В разделе [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)
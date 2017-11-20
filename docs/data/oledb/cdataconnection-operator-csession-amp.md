---
title: "CDataConnection::operator CSession&amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs: C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 526d7957eacaca5c6198c369e08d23e0d3ecc319
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection::operator CSession&amp;
Возвращает ссылку на содержащиеся в нем `CSession` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Этот оператор возвращает ссылку на содержащиеся в нем `CSession` объекта, что позволяет передавать `CDataConnection` объекта где `CSession` ожидается ссылка.  
  
## <a name="example"></a>Пример  
 При наличии функции (такие как `func` ниже), который принимает `CSession` ссылки, можно использовать **CSession &** для передачи `CDataConnection` вместо этого объекта.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDataConnection-класс](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)
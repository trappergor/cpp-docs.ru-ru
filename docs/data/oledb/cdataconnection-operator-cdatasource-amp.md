---
title: "CDataConnection::operator CDataSource&amp; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs:
- C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c52610d947d60fa7ea1be9b764fd09ae0e777a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection::operator CDataSource&amp;
Возвращает ссылку на содержащиеся в нем `CDataSource` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CDataSource&() throw();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Этот оператор возвращает ссылку на содержащиеся в нем `CDataSource` объекта, что позволяет передавать `CDataConnection` объекта где `CDataSource` ожидается ссылка.  
  
## <a name="example"></a>Пример  
 При наличии функции (такие как `func` ниже), который принимает `CDataSource` ссылки, можно использовать **CDataSource &** для передачи `CDataConnection` вместо этого объекта.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDataConnection-класс](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)
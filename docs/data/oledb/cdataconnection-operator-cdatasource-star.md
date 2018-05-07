---
title: CDataConnection::operator CDataSource * | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs:
- C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bade9d813fb9804ae353f7c5139f063f278da225
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
Возвращает указатель на содержащиеся в нем `CDataSource` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CDataSource*() throw();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Этот оператор возвращает указатель на содержащиеся в нем `CDataSource` объекта, что позволяет передавать `CDataConnection` объекта где `CDataSource` требуется указатель.  
  
 В разделе [оператор CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) пример использования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDataConnection-класс](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)
---
title: CDataConnection::operator CSession * | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 97219418f18220cde84c80cb9052f17552a3a45d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094473"
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
Возвращает указатель на содержащиеся в нем `CSession` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
operator const CSession*() throw();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Этот оператор возвращает указатель на содержащиеся в нем `CSession` объекта, что позволяет передавать `CDataConnection` объекта где `CSession` требуется указатель.  
  
## <a name="example"></a>Пример  
 В разделе [оператор CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) пример использования.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CDataConnection-класс](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)
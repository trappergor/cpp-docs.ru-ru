---
title: CDataConnection::CDataConnection | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 267341f88886f3ff94a6b828034e8acbaa2dc0c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Создает и инициализирует `CDataConnection` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ds`  
 [in] Ссылка на существующее подключение к данным.  
  
## <a name="remarks"></a>Примечания  
 Первый переопределение создает новую `CDataConnection` объекта с параметрами по умолчанию.  
  
 Второй переопределение создает новую `CDataConnection` объект с эквивалентный объект подключения к данным, можно указать параметры.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataConnection](../../data/oledb/cdataconnection-class.md)
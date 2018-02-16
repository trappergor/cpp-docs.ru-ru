---
title: "CDataConnection::CDataConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0437f0280578f9e3e2b652e9d4ed01c59ba3ab6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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
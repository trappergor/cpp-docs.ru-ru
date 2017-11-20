---
title: "CDataConnection::CDataConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs: C++
helpviewer_keywords: CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e92019f3f49257e297bddb2f717cf416da62a3bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Создает и инициализирует `CDataConnection` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
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
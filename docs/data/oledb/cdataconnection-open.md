---
title: CDataConnection::Open | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 2c6f0c01-4954-43ba-973e-861ac8e82892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8be130a1270f3782f7f7c47aab4dfb02101a3a3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094225"
---
# <a name="cdataconnectionopen"></a>CDataConnection::Open
Открывает соединение с источником данных с помощью строки инициализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(LPCOLESTR szInitString) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *szInitString*  
 [in] Строка инициализации источника данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataConnection](../../data/oledb/cdataconnection-class.md)
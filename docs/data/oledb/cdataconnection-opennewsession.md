---
title: "CDataConnection::OpenNewSession | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs:
- C++
helpviewer_keywords:
- OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee1d92178d0bb00e6ef3a760a4f775b7854696d2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
Открывает новый сеанс с использованием текущего объекта соединения источника данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `session`  
 [входные/выходные] Ссылка на объект нового сеанса.  
  
 **Заметки**  
 Новый сеанс использует объект источника данных, содержащихся текущего объекта соединения с родительским и можно получить доступ ко всем те же сведения, как источник данных.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataConnection](../../data/oledb/cdataconnection-class.md)
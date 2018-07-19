---
title: CDataConnection::OpenNewSession | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f20f66ec6cc494c14e99c50de4824ba68d27264d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094326"
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